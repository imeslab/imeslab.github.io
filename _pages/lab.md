---
title: "智慧多媒體網路暨嵌入式系統實驗室"
layout: single
permalink: /lab/
author_profile: true
---

## 🏫 實驗室簡介
<p><strong>指導教授：</strong> {{ site.data.lab_info.info.professor }}</p>
<p><strong>學校：</strong> {{ site.data.lab_info.info.university }}</p>
<p><strong>聯絡方式：</strong> Email: <a href="mailto:{{ site.data.lab_info.info.email }}">{{ site.data.lab_info.info.email }}</a></p>
<p><strong>研究室：</strong> {{ site.data.lab_info.info.office }} (分機：{{ site.data.lab_info.info.office_phone }})</p>
<p><strong>實驗室：</strong> {{ site.data.lab_info.info.lab_location }} (分機：{{ site.data.lab_info.info.lab_phone }})</p>

<hr>

## 🎯 專長領域
<ul>
{% for skill in site.data.lab_info.info.expertise %}
  <li>{{ skill }}</li>
{% endfor %}
</ul>

<hr>

## 🔬 研究方向
<ul>
{% for topic in site.data.lab_info.info.research_directions %}
  <li>{{ topic }}</li>
{% endfor %}
</ul>

<hr>