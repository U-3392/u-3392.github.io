---
layout: page
title: /.reference
permalink: /ref/
---
post organization, by tags.

{% assign stag = site.tags | sort %}
{% for tag in stag %}
  <h3>{{ tag[0] }}</h3>
  <ul>
    {% for post in tag[1] %}
      <li>
      {%- assign date_format = "%Y-%m-%d" -%}
      [ {{ post.date | date: date_format }} ]
      <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
      </li>
    {% endfor %}
  </ul>
{% endfor %}