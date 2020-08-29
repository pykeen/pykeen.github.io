---
layout: home
---
<img src="/img/logo.png" alt="PyKEEN Logo" align="left" height="60" style="margin-right: 10px"/>
PyKEEN (**Py**thon **K**nowl**E**dge **E**mbeddi**N**gs) is a Python package designed to train and
evaluate knowledge graph embedding models (incorporating multi-modal information)

GitHub: https://github.com/pykeen/pykeen
Tutorials: https://pykeen.readthedocs.io/en/latest/tutorial/first_steps.html
Twitter: https://twitter.com/keenuniverse

## Getting Started

This example shows how to train a model on a data set and test on another data set.

The fastest way to get up and running is to use the pipeline function. It
provides a high-level entry into the extensible functionality of this package.
The following example shows how to train and evaluate the TransE model on the
Nations dataset. By default, the training loop uses the stochastic local closed
world assumption and evaluates with rank-based evaluation.

```python
from pykeen.pipeline import pipeline

results = pipeline(
     model='TransE',
     dataset='nations',
)
hits_at_10 = results.metric_results.get_metric('hits@10')
```

Full documentation can be found on [ReadTheDocs](https://pykeen.readthedocs.io).

## Installation

PyKEEN can be installed with pip on Python version 3.6+.

```bash
pip install pykeen
```

More information at https://pykeen.readthedocs.io/en/latest/installation.html.

## Citation 

[**PyKEEN 1.0: A Python Library for Training and Evaluating Knowledge Graph Embeddings**](https://arxiv.org/abs/2007.14175).
<br /> Ali, M., Berrendorf, M., Hoyt, C. T., Vermue, L., Sharifzadeh, S., Tresp, V., & Lehmann, J. (2020).
<br /> *arXiv*, **2007.14175**.
