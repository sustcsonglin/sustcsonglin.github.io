---
layout: page
permalink: /talk/
title: Talks
description: invited talks and presentations in reversed chronological order.
nav: true
nav_order: 4
---

<div class="talks">
  {% if site.data.talks and site.data.talks.size > 0 %}
    {%- assign talks = site.data.talks | sort: 'date' | reverse -%}

    <div class="talk-list">
      {% for talk in talks %}
        <article class="talk-card">
          <div class="talk-content">
            <h3 class="talk-title">
              {{ talk.title }}
              {% if talk.or %}
                <span>or</span>
                {{ talk.or }}
              {% endif %}
            </h3>

            <div class="talk-meta">
              <time datetime="{{ talk.date }}"><i class="fas fa-calendar-alt"></i>{{ talk.date }}</time>
              {% if talk.venue or talk.location %}
                {% if talk.venue %}
                  <span><i class="fas fa-university"></i>{{ talk.venue }}</span>
                {% endif %}
                {% if talk.location %}
                  <span><i class="fas fa-map-marker-alt"></i>{{ talk.location }}</span>
                {% endif %}
              {% endif %}
            </div>

            {% if talk.description %}
              <p class="talk-description">
                {{ talk.description }}
              </p>
            {% endif %}

            <div class="talk-links">
              {% if talk.pdf %}
                <a href="{{ talk.pdf | relative_url }}" target="_blank" rel="noopener noreferrer" class="talk-link talk-link-primary" role="button">
                  <i class="fas fa-file-pdf"></i> PDF
                </a>
              {% endif %}

              {% if talk.slides %}
                <a href="{{ talk.slides | relative_url }}" target="_blank" rel="noopener noreferrer" class="talk-link" role="button">
                  <i class="fas fa-chalkboard-teacher"></i> Slides
                </a>
              {% endif %}

              {% if talk.video %}
                <a href="{{ talk.video }}" target="_blank" rel="noopener noreferrer" class="talk-link" role="button">
                  <i class="fas fa-video"></i> Video
                </a>
              {% endif %}
            </div>
          </div>
        </article>
      {% endfor %}
    </div>
  {% else %}
    <p>No talks yet...</p>
  {% endif %}
</div>
