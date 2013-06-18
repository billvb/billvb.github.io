---
title: Home
layout: base
---

I do the bulk of my work these days on the autonomy flight software for NASA's Solar Probe mission at JHUAPL. My secondary pursuit at the lab is in cyber security, specifically concerns relevant to spaceflight and operations.

In the past I've been involved with DTN as it applies to space networks (the "Interplanetary Internet"), and recently I served a stint on the Mission Operations team for the RBSP/VAP mission.

On one hand I work on mission-critical software systems, on the other I'm still a hacker a heart: through some personal projects I've gleaned substantial expertise in Scala, Django, jQuery and a slew of other web technologies.

My e-mail address is [vanbesien@gmail.com](mailto:vanbesien@gmail.com)

## Posts
<table class="flat">
{% for post in site.posts %}
<tr><td><b>{{ post.date | date_to_string }}</b></td><td>&nbsp;&raquo;&nbsp;<a href="{{ post.url }}">{{ post.title }}</a></td></tr>
{% endfor %}
</table>
