---
layout: default
permalink: /blog/models/
title: Models
description: Deep-dives into what a specific model does within a topic — agent-based models, general equilibrium, Kalman filters, and more.
nav: false
---

<div class="post">

  <div class="header-bar">
    <h1>Models</h1>
    <h2>Deep-dives into what a specific model does, within complex systems, econ & politics, sci-tech, or engineering.</h2>
  </div>

{% assign models_posts = site.posts | where: "series", "models" | sort: "date" | reverse %}

  <ul class="post-list">
    {% for post in models_posts %}
    {% assign read_time = post.content | number_of_words | divided_by: 180 | plus: 1 %}
    {% assign year = post.date | date: "%Y" %}
    <li>
      <h3>
        <a class="post-title" href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h3>
      <p>{{ post.description }}</p>
      <p class="post-meta">
        {{ read_time }} min read &nbsp; &middot; &nbsp;
        {{ post.date | date: '%B %d, %Y' }}
      </p>
      <p class="post-tags">
        <a href="{{ year | prepend: '/blog/' | relative_url }}">
          <i class="fa-solid fa-calendar fa-sm"></i> {{ year }}
        </a>
        {% if post.categories.size > 0 %}
        &nbsp; &middot; &nbsp;
        {% for category in post.categories %}
        <a href="{{ category | slugify | prepend: '/blog/category/' | relative_url }}">
          <i class="fa-solid fa-tag fa-sm"></i> {{ category }}
        </a>
        {% unless forloop.last %}&nbsp;{% endunless %}
        {% endfor %}
        {% endif %}
      </p>
    </li>
    {% else %}
    <li>No Models posts yet.</li>
    {% endfor %}
  </ul>

</div>
