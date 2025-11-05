---
layout: archive
title: Songs in the Static
description: ...
---

<div class="glitch" data-text="Songs in the Static">Songs in the Static</div>
<p class="subtitle">Transmission or lullaby (1999)</p>

<hr style="border: 0; border-top: 1px dashed var(--border); margin: 3rem 0;" />

<p>
  You found it.<br>
  That means you’re hearing the static.
</p>

<p>
  Below lies the archive 
</p>

<hr style="border: 0; border-top: 1px dashed var(--border); margin: 4rem 0;" />

{% for category in site.collections %}
  {% if category.label == 'posts' %}
    {% assign posts_by_dir = site.posts | group_by: "dir" %}
    {% for dir_group in posts_by_dir %}
      <h2 id="{{ dir_group.name | slugify }}">{{ dir_group.name | capitalize }}</h2>
      <ul style="list-style: none; padding-left: 0;">
        {% for post in dir_group.items %}
          <li>
            <a href="{{ post.url }}">
              ▶️ {{ post.title }}
            </a>
            <small style="color: var(--accent); margin-left: 0.5rem;">
              {{ post.date | date: "%Y" }}
            </small>
          </li>
        {% endfor %}
      </ul>
    {% endfor %}
  {% endif %}
{% endfor %}
