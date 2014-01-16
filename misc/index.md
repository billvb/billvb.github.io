---
title: Misc
layout: base
---

## Misc Projects

Details on some miscellaneous projects.

## Posts
{% for post in site.posts %}
<p>
<a href="{{ post.url }}"><strong>{{ post.title }}</strong></a><br />
{{ post.date | date_to_string }} </p>
{% endfor %}
