---
layout: default
title: Blog
permalink: /blog/
---
<ul class="post-list">
    {% for post in site.posts %}
    <li>
        {% assign date_format = site.minima.date_format | default: "%b %-d, %Y" %}
        <span class="post-meta">{{ post.date | date: date_format }} {% if post.author %} • {{ post.author }}{% endif %}</span>
        <h2>
            <a class="post-link" href="{{ post.url }}">{{ post.title | escape }}</a>
        </h2>
        {% if post.image %}
        <p>
            <img src="{{post.image}}" alt="Image for {{ post.title }}"/>
        </p>
        {% endif %}
        {{ post.excerpt }}
    </li>
    {% endfor %}
</ul>
<p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" }}">via RSS</a></p>
