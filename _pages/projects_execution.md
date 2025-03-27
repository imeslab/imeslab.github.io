---
title: "計畫執行"
layout: single
permalink: /projects_execution/
author_profile: true
---

## 📑 科技部
<ul>
{% for project in site.data.projects_execution_most.items %}
  <li>
    <p>{{ project.id }}. {{ project.title }}</p>
  </li>
{% endfor %}
</ul>

## 📑 教育部
<ul>
{% for project in site.data.projects_execution_moe.items %}
  <li>
    <p>{{ project.id }}. {{ project.title }}</p>
  </li>
{% endfor %}
</ul>

## 📑 大專學生研究計畫
<ul>
{% for project in site.data.projects_execution_student.items %}
  <li>
    <p>{{ project.id }}. {{ project.title }}</p>
  </li>
{% endfor %}
</ul>