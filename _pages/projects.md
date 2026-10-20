---
layout: default
title: Kyle Dattner - Portfolio
permalink: /projects/
---

<div class="gallery-container">
<div class="project-gallery">
    {% for project in site.projects %}
      {% unless project.gallery == false %}
      <div class="gallery-item">
        <a href="{{ project.url | relative_url }}">
          {% if project.image %}
          <img src="{{ project.image | relative_url }}" alt="{{ project.title }}" />
          {% else %}
          <div class="gallery-placeholder"><span>Work in progress</span></div>
          {% endif %}
          <p>{{ project.title}}</p>
        </a>
      </div>
      {% endunless %}
    {% endfor %}
</div>
</div>