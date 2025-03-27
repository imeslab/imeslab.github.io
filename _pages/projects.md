---
title: "專案介紹"
layout: single
permalink: /projects/
author_profile: true
---

## 🚀 主要專案
<ul>
{% for project in site.data.projects.projects %}
  <li>
    <h2>{{ project.id }}. {{ project.name }}</h2>
    <p>{{ project.description }}</p>
    
    {% for image in project.images %}
      <img class="img-responsive" src="/assets/images/{{ image }}" alt="{{ project.name }}">
    {% endfor %}

    <h3>📌 特色</h3>
    <ul>
      {% for feature in project.features %}
        <li>{{ feature }}</li>
      {% endfor %}
    </ul>

    <h3>💻 支援平台</h3>
    <p>{{ project.platform }}</p>

    <hr>
  </li>
{% endfor %}
</ul>
