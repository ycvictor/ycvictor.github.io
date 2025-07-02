---
layout: page
title: Recipes
permalink: /recipes/
---

_I love snacks and baking brings me joy. If you have any feedback or a secret recipe to share, I’d genuinely love to hear from you._

![cookie](images/cookie.jpeg)

<ul class="recipe-list">
{% for post in site.categories.recipes %}
  <li class="recipe-item">
    <a href="{{ post.url }}">
      <img src="{{ post.thumbnail }}" alt="{{ post.title }} thumbnail" class="recipe-thumb">
      <div class="recipe-info">
        <span class="recipe-title">{{ post.title }}</span>
        <span class="recipe-date">{{ post.date | date: "%B %Y" }}</span>
      </div>
    </a>
  </li>
{% endfor %}
</ul>