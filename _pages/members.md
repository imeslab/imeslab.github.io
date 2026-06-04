---
title: "實驗室成員"
layout: single
permalink: /members/
author_profile: false
classes: wide
---

<style>
  .members-summary {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 10rem));
    gap: 0.75rem;
    margin: 0 0 1.5rem;
  }

  .members-summary__item {
    padding: 0.65rem 0.8rem;
    border: 1px solid rgba(148, 163, 184, 0.28);
    border-radius: 6px;
    background: rgba(148, 163, 184, 0.08);
  }

  .members-summary__label {
    display: block;
    font-size: 0.72rem;
    opacity: 0.76;
  }

  .members-summary__value {
    display: block;
    margin-top: 0.2rem;
    font-size: 1.08rem;
    font-weight: 700;
  }

  .members-list {
    margin: 0.75rem 0 1.8rem;
  }

  .member-record {
    display: grid;
    grid-template-columns: 9.5rem minmax(0, 1fr);
    gap: 0.85rem 1.2rem;
    padding: 0.95rem 0;
    border-top: 1px solid rgba(148, 163, 184, 0.28);
  }

  .member-record:last-child {
    border-bottom: 1px solid rgba(148, 163, 184, 0.28);
  }

  .member-record__meta {
    display: grid;
    gap: 0.26rem;
    align-content: start;
    font-size: 0.72rem;
    line-height: 1.45;
  }

  .member-record__year {
    font-weight: 700;
  }

  .member-record__person {
    font-size: 0.82rem;
    font-weight: 700;
  }

  .member-record__muted {
    opacity: 0.75;
  }

  .member-record__title {
    margin: 0;
    font-size: 0.9rem;
    line-height: 1.45;
    font-weight: 700;
  }

  .member-record__subtext {
    margin: 0.25rem 0 0;
    font-size: 0.74rem;
    line-height: 1.45;
    opacity: 0.76;
  }

  .member-record__keywords {
    display: flex;
    flex-wrap: wrap;
    gap: 0.35rem;
    margin-top: 0.65rem;
  }

  .member-record__keyword {
    display: inline-flex;
    align-items: center;
    max-width: 100%;
    padding: 0.16rem 0.42rem;
    border: 1px solid rgba(148, 163, 184, 0.28);
    border-radius: 5px;
    background: rgba(148, 163, 184, 0.08);
    font-size: 0.64rem;
    line-height: 1.35;
    overflow-wrap: anywhere;
  }

  @media (max-width: 720px) {
    .members-summary {
      grid-template-columns: repeat(2, minmax(0, 1fr));
    }

    .member-record {
      grid-template-columns: 1fr;
      gap: 0.55rem;
    }

    .member-record__meta {
      grid-template-columns: repeat(2, minmax(0, 1fr));
    }
  }
</style>

{% assign graduate_count = site.data.members.graduates | size %}
{% assign undergraduate_count = 0 %}
{% for project in site.data.members.undergraduate_projects %}
  {% assign project_member_count = project.members | size %}
  {% assign undergraduate_count = undergraduate_count | plus: project_member_count %}
{% endfor %}

<div class="members-summary">
  <div class="members-summary__item">
    <span class="members-summary__label">研究生</span>
    <span class="members-summary__value">{{ graduate_count }} 人</span>
  </div>
  <div class="members-summary__item">
    <span class="members-summary__label">專題生</span>
    <span class="members-summary__value">{{ undergraduate_count }} 人</span>
  </div>
</div>

## 研究生

<div class="members-list">
  {% for member in site.data.members.graduates %}
    {% assign keywords = member.keywords | split: "、" %}
    {% assign topic_text = member.topic | strip %}
    <article class="member-record">
      <div class="member-record__meta">
        <span class="member-record__year">{{ member.year }} 年</span>
        <span class="member-record__person">{{ member.name }}</span>
        <span class="member-record__muted">學號：{{ member.student_id }}</span>
        <span class="member-record__muted">{{ member.topic_type }}</span>
      </div>
      <div class="member-record__body">
        {% if topic_text != "" %}
          <h3 class="member-record__title">{{ member.topic }}</h3>
        {% endif %}
        {% if member.topic_en %}
          <p class="member-record__subtext">{{ member.topic_en }}</p>
        {% endif %}
        <div class="member-record__keywords" aria-label="關鍵技術">
          {% for keyword in keywords %}
            <span class="member-record__keyword">{{ keyword | strip }}</span>
          {% endfor %}
        </div>
      </div>
    </article>
  {% endfor %}
</div>

## 專題生

<div class="members-list">
  {% for project in site.data.members.undergraduate_projects %}
    {% assign keywords = project.keywords | split: "、" %}
    <article class="member-record">
      <div class="member-record__meta">
        <span class="member-record__year">{{ project.year }} 年</span>
        <span class="member-record__person">{{ project.members | join: "、" }}</span>
        <span class="member-record__muted">{{ project.topic_type }}</span>
        {% if project.note %}
          <span class="member-record__muted">{{ project.note }}</span>
        {% endif %}
      </div>
      <div class="member-record__body">
        <h3 class="member-record__title">{{ project.topic }}</h3>
        <div class="member-record__keywords" aria-label="關鍵技術">
          {% for keyword in keywords %}
            <span class="member-record__keyword">{{ keyword | strip }}</span>
          {% endfor %}
        </div>
      </div>
    </article>
  {% endfor %}
</div>
