---
layout: page
title: Archive
---

{% for tag in site.tags %}
  <h3>{{ tag[0] }}</h3>
  <ul>
    {% assign tag_posts = tag[1] | where: "published", true %}
    {% for post in tag_posts %}
      <li><a href="{{ post.url }}">{{ post.date | date: "%B %Y" }} - {{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}