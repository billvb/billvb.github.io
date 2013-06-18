---
title: Posts
layout: base
---

<style>
table {
 border: 0;
 padding: 0;
 margin: 0;
}
td, tr {
 border: 0;
 margin: 0;
 padding: 0;
}
</style>
<table>
{% for post in site.posts %}
<tr><td><b>{{ post.date | date_to_string }}</b></td><td>&nbsp;&raquo;&nbsp;<a href="#{{post.date}}">{{ post.title }}</a></td></tr>
{% endfor %}
</table>
<br>
{% for post in site.posts %}
<a name="{{ post.date }}"> </a>
<div class="post_entry">
<span class="date">{{ post.date | date_to_string }}</span>

{{ post.content }}

<p>
<a href="{{ post.url }}">[ permalink ]</a> 
</p>

</div>
{% endfor %}

