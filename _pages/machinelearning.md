---
layout: archive
permalink: /machine-learning/
title: "Machine Learning Posts"
author_profile: true
header:
  image: "/images/loss-landscape.jpg"
  overlay_filter: 0.5
  caption: "Photo credit: [Loss Landscape](https://losslandscape.com/)"
---

{% include group-by-array collection=site.posts field="tags" %}

{% for tag in group_names %}
  {% assign posts = group_items[forloop.index0] %}
  <h2 id="{{ tag | slugify }}" class="archive__subtitle">{{ tag }}</h2>
  {% for post in posts %}
    {% if post.is_note != true %}
      {% include archive-single.html %}
    {% endif %}
  {% endfor %}
{% endfor %}
