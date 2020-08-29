---
layout: home
---
<img src="/img/logo.png" alt="PyKEEN Logo" align="left" height="60" style="margin-right: 10px"/>
PyKEEN (**Py**thon **K**nowl**E**dge **E**mbeddi**N**gs) is a Python package designed to train and
evaluate knowledge graph embedding models (incorporating multi-modal information)

## Getting Started

### Installation

The development version of PyKEEN can be downloaded and installed from
[PyPI](https://pypi.org/project/pykeen/) on Python 3.7+ with:

```bash
pip install pykeen
```

The source code can be found on [GitHub](https://github.com/pykeen/pykeen) for installation
in development mode with:

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
Nations dataset. By default, the training loop uses the stochastic local closed
world assumption and evaluates with rank-based evaluation.

```python
from pykeen.pipeline import pipeline
pipeline_result = pipeline(
     model='TransE',
     dataset='nations',
)
hits_at_10 = pipeline_result.metric_results.get_metric('hits@10')
```

Full documentation can be found on [ReadTheDocs](https://pykeen.readthedocs.io).
