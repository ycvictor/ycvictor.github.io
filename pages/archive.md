---
layout: page
title: Archive
---

{% assign tag_order = "Review,Other" | split: "," %}
{% assign ordered_tags = "" | split: "," %}
{% for name in tag_order %}
  {% if site.tags[name] %}{% assign ordered_tags = ordered_tags | push: name %}{% endif %}
{% endfor %}
{% for tag in site.tags %}
  {% unless tag_order contains tag[0] %}{% assign ordered_tags = ordered_tags | push: tag[0] %}{% endunless %}
{% endfor %}

<div class="archive">
{% for tag_name in ordered_tags %}
  {% assign tag_posts = site.tags[tag_name] | where: "published", true | sort: "date" | reverse %}
  {% if tag_posts.size > 0 %}
  <section class="archive-section">
    <h2 class="archive-heading">
      <span>{{ tag_name }}</span>
      <span class="archive-count">{{ tag_posts.size }}</span>
    </h2>

    {% assign years = tag_posts | group_by_exp: "post", "post.date | date: '%Y'" %}
    {% for year in years %}
    <div class="archive-year">
      <h3 class="archive-year-label">{{ year.name }}</h3>
      <ul class="archive-list">
        {% for post in year.items %}
        <li class="archive-item">
          <a class="archive-link" href="{{ post.url | relative_url }}">
            <time class="archive-date" datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%b %d" }}</time>
            <span class="archive-title">{{ post.title }}</span>
          </a>
        </li>
        {% endfor %}
      </ul>
    </div>
    {% endfor %}
  </section>
  {% endif %}
{% endfor %}
</div>
