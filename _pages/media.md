---
layout: default
permalink: /media/
title: media
description: Video/vlog entries and podcast episodes.
nav: true
nav_order: 5
display_categories: [complex-systems, econ-politics, sci-tech, engineering]
---

<div class="post">

  <div class="header-bar">
    <h1>Media</h1>
    <h2>{{ page.description }}</h2>
  </div>

{% if page.display_categories and page.display_categories.size > 0 %}

  <div class="tag-category-list">
    <ul class="p-0 m-0">
      {% for category in page.display_categories %}
      <li>
        <a href="{{ category | slugify | prepend: '/media/tag/' | relative_url }}">{{ category }}</a>
      </li>
      {% unless forloop.last %}<p>&bull;</p>{% endunless %}
      {% endfor %}
    </ul>
  </div>
  {% endif %}

{% assign media_items = site.media | sort: "date" | reverse %}

  <div class="row row-cols-1 row-cols-md-2">
    {% for item in media_items %}
    <div class="col mb-4">
      <a href="{{ item.url | relative_url }}" style="text-decoration: none;">
        <div class="card h-100 hoverable">
          <div class="card-body">
            <span class="post-tags">
              {% if item.media_type == "podcast" %}<i class="fa-solid fa-podcast"></i> Podcast{% else %}<i class="fa-solid fa-video"></i> Video{% endif %}
            </span>
            <h2 class="card-title">{{ item.title }}</h2>
            <p class="card-text">{{ item.description }}</p>
            {% if item.tags.size > 0 %}
            <p class="post-tags">
              {% for topic in item.tags %}
              <span class="category-badge">{{ topic }}</span>
              {% endfor %}
            </p>
            {% endif %}
          </div>
        </div>
      </a>
    </div>
    {% else %}
    <p>No media items yet.</p>
    {% endfor %}
  </div>

</div>
