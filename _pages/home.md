---
title: Blog
layout: splash
permalink: /
date: 2021-01-25
header:
  overlay_color: "#F5DCE1"
  overlay_filter: "0.5"
  overlay_image: https://blog.yinandyams.tk/assets/images/header.jpg
  actions:
    - label: "shop"
      url: "https://yinandyams.tk"
  caption: "Property of Yin & Yams"
  excerpt: ""
---

{{ content }}

<h3 class="archive__subtitle">{{ site.data.ui-text[site.locale].recent_posts | default: "Recent Posts" }}</h3>

{% if paginator %}
  {% assign posts = paginator.posts %}
{% else %}
  {% assign posts = site.posts %}
{% endif %}

{% assign entries_layout = page.entries_layout | default: 'grid' %}
<div class="entries-{{ entries_layout }}">
  {% for post in posts %}
    {% include archive-single.html type=entries_layout %}
  {% endfor %}
</div>

{% include paginator.html %}
