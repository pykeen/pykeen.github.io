---
layout: home
---
<img src="/img/logo.png" alt="PyKEEN Logo" align="left" height="60" style="margin-right: 10px"/>
PyKEEN (**Py**thon **K**nowl**E**dge **E**mbeddi**N**gs) is a Python package designed to train and
evaluate knowledge graph embedding models (incorporating multi-modal information)


## Getting Started

### Installation

The development version of PyKEEN can be downloaded and installed from
[GitHub](https://github.com/pykeen/pykeen) on Python 3.7+ with:

```bash
$ git clone https://github.com/pykeen/pykeen
$ cd pykeen
$ pip install -e .
```

### Training Wheels

This example shows how to train a model on a data set and test on another data set.

The fastest way to get up and running is to use the pipeline function. It
provides a high-level entry into the extensible functionality of this package.
The following example shows how to train and evaluate the TransE model on the
Nations dataset. By default, the training loop uses the open world assumption
and evaluates with rank-based evaluation.

```python
from pykeen.pipeline import pipeline
pipeline_result = pipeline(
     model='TransE',
     dataset='nations',
)
hits_at_10 = pipeline_result.metric_results.get_metric('hits@10')
```

## Applications

Below we highlight recent theoretical and applied uses of PyKEEN.

## Benchmarking Study

<img src="/img/fb15k237.png" alt="FB15k237 Summary" />

We've run an unprecedented large benchmarking study. This image describes the results
on the FB15k237 dataset across several knowledge graph embedding models, loss functions,
training approaches, and usages of explicit modeling of inverse triples. This is just one
of several datasets analyzed in this study. In our manuscript, we also assess the reproducibility
of old models' best reported hyperparameters.

## Metaresearch Recommendations

<img src="/img/metaresearch.png" alt="Metaresearch Schema" />

We used PyKEEN to train a scholarly recommendations system to suggest
papers to read, grants to apply to, and collaborations to make.


## Pathway Crosstalk Analysis

<img src="/img/pathways.png" alt="Pathway Crosstalk Schema" />

We used PyKEEN to train a pathway crosstalk analysis platform that identifies
which biological pathways are connected, giving further insight into normal
human pathophysiology and potentially leading to novel hypotheses for understanding 
the aetiology of complex disease leading to novel drug discovery.
