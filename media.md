---
title: Media・メディア
permalink: /media/
eyebrow: Selected Work
intro: Articles and publications by Omer across journalism and creative writing.
---
<div class="stack">
  {% assign media_entries = site.media | sort: "date" | reverse %}
  {% for item in media_entries %}
    <article class="list-card">
      <p class="card-meta">
        {{ item.date | date: "%B %-d, %Y" }}
        {% if item.publication %} · {{ item.publication }}{% endif %}
      </p>
      <h2><a href="{{ item.external_url }}" target="_blank" rel="noopener noreferrer">{{ item.title }}</a></h2>
    </article>
  {% endfor %}
</div>
