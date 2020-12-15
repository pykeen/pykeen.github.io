---
layout: post
title: Performance Optimizations: ComplEx interaction function 
author: Max Berrendorf
date: 2020-12-?? 00:00:00 -0800
---
Providing performant code is one of the main objectives of the pykeen development team:
Having performant code allows users to faster train and evaluate models, thus accelerating model search and inference.
It also improves resource utilization and since it likely avoids unnecessary computations, also improves environmental impact.

The computational bottleneck of training and evaluating Knowledge Graph Embedding Models (KGEM) usually lies in their interaction function:
Whenever, we compute scores for a triple we need to evaluate it.
<!-- TODO: add trace for training loop -->
Thus, optimizing the interaction function's implementation is the primary target for optimizing overall runtime.

Before we dive into the optimization let us first revisit the use cases within a link prediction pipeline.
* SLCWA: 1:1 / 1:k
* LCWA / Evaluation: 1:n


We can generalize the score function to support all the aforementioned use cases (and even a few more, like full CWA training) to the general form of the interaction function
```python
import torch

def score(h: torch.FloatTensor, r: torch.FloatTensor, t: torch.FloatTensor):
    """
    :param h: shape: (batch_size, num_heads, dim)
        The head representations.
    :param r: shape: (batch_size, num_relations, dim)
        The relation representations.
    :param t: shape: (batch_size, num_tails, dim)
        The tail representations.
        
    :return: shape: (batch_size, num_heads, num_relations, num_tails)
        The scores.
    """
```
with the following input shapes for the individual use cases 
| Use Case | h | r | t | 
| -- | -- | -- | -- |
| score_hrt (naive, 1:1) | (b * (s + 1), 1, d) | (b * (s + 1), 1, d) | (b * (s + 1), 1, d) |
| score_hrt (fast h, 1:k) | (b, s + 1, d) | (b, 1, d) | (b, 1, d) |
| score_hrt (fast t, 1:k) | (b, 1, d) | (b, 1, d) | (b, s + 1, d) |
| score_h (1:n) | (1, n, d) | (b, 1, d) | (b, 1, d) |
| score_t (1:n) | (b, 1, d) | (b, 1, d) | (1, n, d) |

In this blog post, we will exemplify how we optimize interaction function implementation at the example of ComplEx.
For head, relation and tail representations $h, r, t \in \mathbb{C}^d$, the ComplEx interaction function is given by 
```math
score(h, r, t) = Re(<h, r, conj(t)>)
               = <Re(h), Re(r), Re(t)> - <Re(h), Im(r), -Im(t)> - <Im(h), Re(r), -Im(t)>  - <Im(h), Im(r), Re(t)>
               = <Re(h), Re(r), Re(t)> + <Re(h), Im(r), Im(t)> + <Im(h), Re(r), Im(t)>  - <Im(h), Im(r), Re(t)>
```

Notably, we can write
```math
score(h, r, t) = Re(<h \odot r, conj(t)>) = Re(<h, r \odot conj(t)>) 
```
* expected cost (hr)t / h(rt)