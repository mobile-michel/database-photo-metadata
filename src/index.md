---
title: Links
layout: base
---

Description: {{ site.description }}

{% for i in iptc %}
- **{{ i.chapter }}**
  {% assign content = iptc | where: "chapter", i.chapter %}
  {% for item in content[0].items %}
  - **<a href="{{item.url}}" target="_blank">{{item.title}}</a>**: {{item.description}}
  {% endfor %}
{% endfor %}