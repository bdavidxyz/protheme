---
layout: page
title: Writings
permalink: /writings/
---

<div class="writings">
{% for post in site.posts %}
{% assign currentdate = post.date | date: "%Y" %}
{% if currentdate != date %}
{% unless forloop.first %}</ul>{% endunless %}
<h3 id="y{{post.date | date: "%Y"}}">{{ currentdate }}</h3>
<ul>
{% assign date = currentdate %}
{% endif %}
<li><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></li>
{% if forloop.last %}</ul>{% endif %}
{% endfor %}
</div>
