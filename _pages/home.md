---
title: Home
layout: splash
permalink:home/
date: 2021-01-25
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: http://dylanbabel.tk/yinandyams/assets/images/header1.JPG
---

{{ content }}

<h3 class="archive__subtitle">{{ site.data.ui-text[site.locale].recent_posts | default: "Recent Posts" }}</h3>

{% if paginator %}
  {% assign posts = paginator.posts %}
{% else %}
  {% assign posts = site.posts %}
{% endif %}

{% assign entries_layout = page.entries_layout | default: 'list' %}
<div class="entries-{{ entries_layout }}">
  {% for post in posts %}
    {% include archive-single.html type=entries_layout %}
  {% endfor %}
</div>

{% include paginator.html %}