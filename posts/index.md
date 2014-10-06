---
title: Posts
layout: base
---

<h2>Posts</h2>
<table class="flat">
{% for post in site.posts %}
<tr>
<td><b>&raquo; {{ post.date | date_to_string }}</b></td>
<td><a href="{{ post.url }}">{{ post.title }}</a></td>
<td>
<img src="{{post.thumbnail}}" style="width: 100px;" />
</td>
<td>cat</td>
</tr>
{% endfor %}
</table>
<br />
<hr />
{% for post in site.posts %}
<div class="post_entry">
<span class="date">{{ post.date | date_to_string }}</span>

<h2>{{ post.title }}</h2>



{{ post.content }}

<p>
<a href="{{ post.url }}">[ permalink ]</a> 
</p>

</div>
{% endfor %}

