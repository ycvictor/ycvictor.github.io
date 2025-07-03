---
layout: page
title: Recipes
permalink: /recipes/
---

_I love snacks and baking brings me joy. If you have any feedback or a secret recipe to share, I’d genuinely love to hear from you._

<br>

<ul class="recipe-list">
{% assign sorted_recipes = site.recipes | sort: 'date' | reverse %}
{% for recipe in sorted_recipes %}
  <li class="recipe-item">
    <a href="{{ recipe.url }}">
      <img src="{{ recipe.thumbnail | relative_url }}" alt="{{ recipe.title }} thumbnail" class="recipe-thumb">
      <div class="recipe-info">
        <span class="recipe-title">{{ recipe.title }}</span>
        <span class="recipe-date">{{ recipe.date | date: "%B %Y" }}</span>
      </div>
    </a>
  </li>
{% endfor %}
</ul>
