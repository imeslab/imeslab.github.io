---
title: "實驗室資訊"
layout: single
permalink: /lab/
author_profile: true
---

## 🏫 實驗室簡介
<p><strong>實驗室名稱：</strong> {{ site.data.lab_info.info.lab_name }}</p>
<p><strong>英文名稱：</strong> {{ site.data.lab_info.info.lab_name_en }}</p>
<p><strong>指導教授：</strong> {{ site.data.lab_info.info.professor }}</p>
<p><strong>學校：</strong> {{ site.data.lab_info.info.university }}</p>
<p><strong>聯絡方式：</strong> Email: <a href="mailto:{{ site.data.lab_info.info.email }}">{{ site.data.lab_info.info.email }}</a></p>
<p><strong>目前研究室：</strong> {{ site.data.lab_info.info.office }} (分機：{{ site.data.lab_info.info.office_phone }})</p>
<p><strong>目前實驗室：</strong> {{ site.data.lab_info.info.lab_location }} (分機：{{ site.data.lab_info.info.lab_phone }})</p>
<p><strong>{{ site.data.lab_info.info.future_lab_effective_date }}實驗室新地點：</strong> {{ site.data.lab_info.info.future_lab_location }}（分機：{{ site.data.lab_info.info.future_phone }}）</p>

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
