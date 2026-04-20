---
title: Travel Log
permalink: /travel-log/
eyebrow: Field Notes
intro: Notes, stories, and reflections from the road.
---
<div class="stack">
  {% assign logs = site.travel_logs | sort: "date" | reverse %}
  {% for log in logs %}
    <article class="list-card">
      <p class="card-meta">{{ log.date | date: "%B %-d, %Y" }}{% if log.destination %} · {{ log.destination }}{% endif %}</p>
      <h2><a href="{{ log.url | relative_url }}">{{ log.title }}</a></h2>
      {% if log.summary %}
        <p>{{ log.summary }}</p>
      {% else %}
        <p>{{ log.excerpt | strip_html | truncatewords: 28 }}</p>
      {% endif %}
    </article>
  {% endfor %}
</div>
