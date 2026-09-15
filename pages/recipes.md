---
layout: page
title: Recipes
permalink: /recipes/
---

I love snacks, and I bake mostly because I believe desserts are a perfectly valid hobby. If you have feedback or a secret recipe, please share. My stomach and I would greatly appreciate it.

<br>

<ul class="recipe-list">
{% assign sorted_recipes = site.recipes | where: "published", true | sort: 'date' | reverse %}
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
