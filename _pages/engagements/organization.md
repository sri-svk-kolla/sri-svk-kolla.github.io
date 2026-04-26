---
title: "Organizations"
permalink: /engagements/organization/
layout: page
images:
  slider: true
nav: false  # typically children don't appear as top-level nav
---

## Conference and Event Organization

{% for event in site.data.organization %}
  <div class="card mb-4 shadow-sm position-relative">
    <div class="row g-0">
      <div class="col-md-4">
        {% if event.images.size > 1 %}
          <swiper-container keyboard="true"
                            navigation="true"
                            pagination="true"
                            pagination-clickable="true"
                            pagination-dynamic-bullets="true"
                            rewind="true"
                            class="mb-3">
            {% for img in event.images %}
              <swiper-slide>
                <div class="slider-image-container">
                  {% include figure.liquid path=img class="img-fluid rounded z-depth-1" %}
                </div>
              </swiper-slide>
            {% endfor %}
          </swiper-container>
        {% else %}
          {% assign img_path = event.images[0] %}
          <div class="slider-image-container">
            {% include figure.liquid path=img_path class="img-fluid rounded-start w-100" %}
          </div>
        {% endif %}
      </div>

      <div class="col-md-8">
        <div class="card-body position-relative">
          <h5 class="card-title">
            {% if event.link %}
              <a href="{{ event.link }}" target="_blank" rel="noopener noreferrer" class="stretched-link text-decoration-none text-reset">
                {{ event.title }} 🔗
              </a>
            {% else %}
              {{ event.title }}
            {% endif %}
          </h5>
          <p><strong>Role:</strong> {{ event.role }}</p>
          <p>{{ event.description }}</p>
        </div>
      </div>
    </div>
  </div>
{% endfor %}