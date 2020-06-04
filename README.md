---
layout: home
---
<img src="/img/logo.png" alt="PyKEEN Logo" align="left" height="60" style="margin-right: 10px"/>
PyKEEN (**Py**thon **K**nowl**E**dge **E**mbeddi**N**gs) is a Python package designed to train and
evaluate knowledge graph embedding models (incorporating multi-modal information)

<ul>
{% for entry in site.data.publications %}
<li>[{{ entry.name }}]({{ entry.url }})</li>
{% endfor %}
</ul>
