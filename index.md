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

Train the TransE model on the Nations dataset with:

```python
from pykeen.pipeline import pipeline

results = pipeline(model='TransE', dataset='Nations')
hits_at_10 = results.get_metric('hits@10')
```

The default training loop uses the stochastic local closed world assumption, uniform negative sampling, and evaluates
with rank-based evaluation. How to configure these options, and more, are included in the
[documentation](https://pykeen.readthedocs.io).

## Installation

PyKEEN can be installed with `pip` on Python version 3.7+. More details on
[Read the Docs](https://pykeen.readthedocs.io/en/latest/installation.html).

```shell
$ pip install pykeen
```

## History

- October 21, 2021: The PyKEEN large-scale benchmarking paper is accepted for
  publication in [TPAMI](https://doi.org/10.1109/TPAMI.2021.3124805).
- March 5, 2021: The PyKEEN 1.0 software paper is accepted for publication in
  [JMLR](http://jmlr.org/papers/v22/20-825.html).
- July 28, 2020: With all the improvements made to support the PyKEEN benchmarking paper, the PyKEEN 1.0 software paper
  is posted to [arXiv](https://arxiv.org/abs/2007.14175).
- June 25, 2020: PyKEEN version [1.0.0](https://pypi.org/project/pykeen/1.0.0/) is published to PyPI to complement the
  large-scale benchmarking paper.
- June 23, 2020: After nearly a year of work, the PyKEEN large-scale benchmarking paper is posted
  to [arXiv](https://arxiv.org/abs/2006.13365).
- August 2019: PyKEEN joins Twitter [@keenuniverse](https://twitter.com/keenuniverse).
- April 2019: Max Berrendorf, Laurent Vermue, and Sahand Sharifzadeh join the team.
- February 13, 2019: The PyKEEN biological application manuscript is accepted
  by [Oxford Bioinformatics](https://doi.org/10.1093/bioinformatics/btz117).
- November 23, 2018: The PyKEEN's biological application preprint is posted
  to [bioRxiv](https://www.biorxiv.org/content/10.1101/475202v1).
- October 9, 2018: Our first release on [PyPI](https://pypi.org/project/pykeen/0.0.1/) and first build
  on [ReadTheDocs](https://readthedocs.org/projects/pykeen/builds/7912003/).
- July 2019: Charles Tapley Hoyt and Daniel Domingo-Fernández join the team.
- June 6, 2018: Our first [commit](https://github.com/pykeen/pykeen/commit/00dc2237cdbb46536d98068546bc7a801ae4126d) on
  GitHub. Initially, this repository was authored by Mehdi Ali under
  the [Smart Data Analytics](https://github.com/smartdataanalytics/)
  organization, but as the project and the team grew, we moved it to its own organization.

## Citation

[**PyKEEN 1.0: A Python Library for Training and Evaluating Knowledge Graph
Embeddings**](http://jmlr.org/papers/v22/20-825.html).
<br /> Ali, M., Berrendorf, M., Hoyt, C. T., Vermue, L., Sharifzadeh, S., Tresp, V., & Lehmann, J. (2020).
<br /> *Journal of Machine Learning Research*, **22**(82), 1–6.

BibTeX Entry:

```bibtex
@article{pykeen2021software,
    author = {Ali, Mehdi and Berrendorf, Max and Hoyt, Charles Tapley and Vermue, Laurent and Sharifzadeh, Sahand and Tresp, Volker and Lehmann, Jens},
    journal = {Journal of Machine Learning Research},
    number = {82},
    pages = {1--6},
    title = {% raw %}{{PyKEEN 1.0: A Python Library for Training and Evaluating Knowledge Graph Embeddings}}{% endraw %},
    url = {https://jmlr.org/papers/v22/20-825.html},
    volume = {22},
    year = {2021}
}
```

[**Bringing Light Into the Dark: A Large-scale Evaluation of Knowledge Graph Embedding Models under a Unified Framework**](https://doi.org/10.1109/TPAMI.2021.3124805)
<br />Ali, M., Berrendorf, M., Hoyt, C.T., Vermue, L., Galkin, M., Sharifzadeh, S., Fischer, A., Tresp, V., & Lehmann, J. (2021).
<br /> *Transactions on Pattern Analysis and Machine Intelligence*, **2021**.

BibTeX Entry:

```bibtex
@article{pykeen2021benchmarking,
  author = {Ali, Mehdi and Berrendorf, Max and Hoyt, Charles Tapley and Vermue, Laurent and Galkin, Mikhail and Sharifzadeh, Sahand and Fischer, Asja and Tresp, Volker and Lehmann, Jens},
  journal = {IEEE Transactions on Pattern Analysis and Machine Intelligence}, 
  title = {% raw %}{{Bringing Light Into the Dark: A Large-scale Evaluation of Knowledge Graph Embedding Models under a Unified Framework}}{% endraw %},
  year = {2021},
  pages = {1-1},
  doi = {10.1109/TPAMI.2021.3124805},
  url = {https://doi.org/10.1109/TPAMI.2021.3124805}
}
```
