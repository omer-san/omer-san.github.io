---
title: Testimonials・推薦文
permalink: /testimonials/
eyebrow: Client Reviews
---
<div class="testimonial-grid">
  {% assign reviews = site.testimonials | sort: "date" | reverse %}
  {% for review in reviews %}
    <article class="testimonial-card">
      <div class="testimonial-content">
        <p class="card-meta">{{ review.client_name }}{% if review.from %} from {{ review.from }}{% endif %}</p>
        <h2><a href="{{ review.url | relative_url }}">{{ review.title }}</a></h2>
        <div class="testimonial-text">
          {{ review.content | markdownify }}
        </div>
        {% if review.images and review.images.size > 0 %}
          <div class="thumb-row thumb-row-gallery">
            {% for image in review.images %}
              <a class="thumb-link" href="{{ image | relative_url }}">
                <img src="{{ image | relative_url }}" alt="{{ review.client_name }} gallery image {{ forloop.index }}">
              </a>
            {% endfor %}
          </div>
        {% endif %}
      </div>
    </article>
  {% endfor %}
</div>
