---
title: Posts
layout: base
---

{% for post in site.posts %}
<div class="post_entry">
<span class="date">{{ post.date | date_to_string }}</span>

{{ post.content }}

<p>
<a href="{{ post.url }}">[ permalink ]</a> 
</p>

</div>
{% endfor %}

