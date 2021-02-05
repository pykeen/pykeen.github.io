---
layout: home
---
<img src="/img/logo.png" alt="PyKEEN Logo" align="left" height="60" style="margin-right: 10px"/>
PyKEEN (**Py**thon **K**nowl**E**dge **E**mbeddi**N**gs) is a Python package designed to train and
evaluate knowledge graph embedding models (incorporating multi-modal information)

Find us on:

- [GitHub](https://github.com/pykeen/pykeen) ![GitHub stars](https://img.shields.io/github/stars/pykeen/pykeen?label=PyKEEN%20on%20GitHub&style=social)
- [Twitter](https://twitter.com/keenuniverse) ![Twitter Follow](https://img.shields.io/twitter/follow/keenuniverse?style=social)
- [Tutorials](https://pykeen.readthedocs.io/en/latest/tutorial/first_steps.html)

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
<br /> *arXiv*, 2007.14175.

## History

- July 28, 2020: With all the improvements made to support the PyKEEN benchmarking paper, the PyKEEN 1.0 paper is
  published to [arXiv](https://arxiv.org/abs/2007.14175).
- June 23, 2020: After nearly a year of work, the PyKEEN large-scale benchmarking paper is published
  to [arXiv](https://arxiv.org/abs/2006.13365).
- April 2019: Max Berrendorf, Laurent Vermue, and Sahand Sharifzadeh join the team.
- February 13, 2019: The PyKEEN biological application manuscript is accepted
  by [Oxford Bioinformatics](https://doi.org/10.1093/bioinformatics/btz117).
- November 23, 2018: The PyKEEN's biological application preprint is published
  on [bioRxiv](https://www.biorxiv.org/content/10.1101/475202v1)
- October 9, 2018: Our first release on [PyPI](https://pypi.org/project/pykeen/0.0.1/) and first build
  on [ReadTheDocs](https://readthedocs.org/projects/pykeen/builds/7912003/).
- July 2019: Charles Tapley Hoyt and Daniel Domingo-Fernández join the team.
- June 6, 2018: Our first [commit](https://github.com/pykeen/pykeen/commit/00dc2237cdbb46536d98068546bc7a801ae4126d) on
  GitHub. Initially, this repository was authored by Mehdi Ali under
  the [Smart Data Analytics](https://github.com/smartdataanalytics/)
  organization, but as the project and the team grew, we moved it to its own organization.
