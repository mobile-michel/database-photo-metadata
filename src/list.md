---
title: IPTC fields
description: List of IPTC fields by category
layout: base
tags: primary
---

Description: {{ description }}

{% assign item = database | map: "category" | uniq %}
{% for firstArray in item %}
- {{ firstArray }}
  {% assign content = database | where: "category", firstArray %}
  {% for secondArray in content %}
  - <a href="/details/{{ secondArray.field | slugify }}">{{ secondArray.field }}</a>
  {% endfor %}
{% endfor %}