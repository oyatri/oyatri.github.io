---
layout: archive
permalink: algorithm
title: "ALGORITHM"

author_profile: true
sidebar:
  nav: "docs"
classes: wide
---

---

<!-- {% if paginator %}
  {% assign posts = paginator.posts %}
{% else %}
  {% assign posts = site.posts %}
{% endif %} -->

{% assign posts = site.categories.Algorithm %}

{% assign entries_layout = page.entries_layout | default: 'list' %}
<div class="entries-{{ entries_layout }}">
  {% for post in posts %}
    {% include archive-single.html type=entries_layout %}
  {% endfor %}
</div>

{% include paginator.html %}