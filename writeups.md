---
layout: page
title: Writeups
keywords: rtfm ctf writeups
---

<div class="posts posts">
  {% for post in site.posts %}
    <div class="post-list">
      <div class="post-list-date"><small>{{ post.date | date: "%b %d, %Y" }}</small></div>
	    <div class="text-truncate"><a href="{{ post.url }}">{{ post.title }}</a></div>
      <div class="post-list-desc">{{ post.description }}</div>
    </div>
  {% endfor %}
</div>
