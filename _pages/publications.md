---
title: "論文發表"
layout: single
permalink: /publications/
author_profile: true
---

## 📚 期刊論文
<ul>
{% assign num = 1 %}
{% assign sorted_papers = site.data.journal_papers.papers %}

{% for paper in sorted_papers %}
  <li>
    <strong>{{ num }}.</strong> {{ paper.authors }}, “{{ paper.title }},” <i>{{ paper.journal }}</i>, Vol. {{ paper.volume }}, pp. {{ paper.pages }}, {{ paper.year }} 
    {% if paper.index %} ({{ paper.index }}){% endif %}
    <!--{% if paper.link %} 🔗 <a href="{{ paper.link }}" target="_blank">閱讀全文</a>{% endif %}-->
  </li>
  {% assign num = num | plus: 1 %}
{% endfor %}
</ul>

## 🎤 國際會議論文
<ul>
{% assign num = 1 %}
{% assign sorted_papers = site.data.conference_papers.papers %}

{% for paper in sorted_papers %}
  <li>
    <strong>{{ num }}.</strong> {{ paper.authors }}, “{{ paper.title }},” <i>{{ paper.journal }}</i>, Vol. {{ paper.volume }}, pp. {{ paper.pages }}, {{ paper.year }} 
    {% if paper.index %} ({{ paper.index }}){% endif %}
    <!--{% if paper.link %} 🔗 <a href="{{ paper.link }}" target="_blank">閱讀全文</a>{% endif %}-->
  </li>
  {% assign num = num | plus: 1 %}
{% endfor %}
</ul>
