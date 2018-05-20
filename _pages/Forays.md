---
layout: archive
permalink: /forays/
title: "botany forays"
author_profile: false
sidebar:
  nav: "docs"
toc: true
---


{% assign postsByYear = site.posts | where: "categories","forays" | group_by_exp:"post", "post.date | date: '%Y'" %}
{% for year in postsByYear %}
  ## id="{{ year.name | slugify }}" class="archive__subtitle">{{ year.name }}
  {% for post in year.items %}
    {% include archive-single.html %}
  {% endfor %}
{% endfor %}