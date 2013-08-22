---
title: Misc
layout: base
---

## Misc Projects

Details on some miscellaneous projects.

## Posts
<table class="flat">
{% for post in site.posts %}
<tr><td><b>{{ post.date | date_to_string }}</b></td><td>&nbsp;&raquo;&nbsp;<a href="{{ post.url }}">{{ post.title }}</a></td></tr>
{% endfor %}
</table>
