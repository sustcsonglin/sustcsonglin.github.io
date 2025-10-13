---
layout: page
permalink: /talk/
title: talks
description: invited talks and presentations in reversed chronological order.
nav: true
nav_order: 4
---

<div class="talks">
  {% if site.data.talks and site.data.talks.size > 0 %}
    {%- assign talks = site.data.talks | sort: 'date' | reverse -%}
    
    <div class="table-responsive">
      <table class="table table-sm table-borderless">
        {% for talk in talks %}
          <tr>
            <th scope="row" style="width: 15%; vertical-align: top; padding-top: 1rem;">
              {{ talk.date | date: "%b %-d, %Y" }}
            </th>
            <td style="padding-top: 1rem;">
              <div class="talk-entry">
                <strong class="talk-title">
                  {{ talk.title }}
                  {% if talk.or %}
                    <span style="font-weight: normal; color: var(--global-text-color-light);"> or </span>{{ talk.or }}
                  {% endif %}
                </strong>
                
                {% if talk.venue or talk.location %}
                  <div class="talk-venue" style="color: var(--global-text-color-light); margin-top: 0.25rem;">
                    {% if talk.venue %}
                      <i class="fas fa-university" style="margin-right: 0.3rem;"></i>{{ talk.venue }}
                    {% endif %}
                    {% if talk.location %}
                      {% if talk.venue %}
                        <span style="margin-left: 0.5rem;">
                          <i class="fas fa-map-marker-alt" style="margin-right: 0.3rem;"></i>{{ talk.location }}
                        </span>
                      {% else %}
                        <i class="fas fa-map-marker-alt" style="margin-right: 0.3rem;"></i>{{ talk.location }}
                      {% endif %}
                    {% endif %}
                  </div>
                {% endif %}
                
                {% if talk.description %}
                  <div class="talk-description" style="margin-top: 0.5rem; font-size: 0.9rem;">
                    {{ talk.description }}
                  </div>
                {% endif %}
                
                <div class="talk-links" style="margin-top: 0.75rem;">
                  {% if talk.pdf %}
                    <a href="{{ talk.pdf | relative_url }}" target="_blank" class="btn z-depth-1" role="button" style="font-size: 0.95rem; padding: 0.5rem 1.2rem; background-color: var(--global-theme-color); color: white; font-weight: 500; border-radius: 0.3rem;">
                      <i class="fas fa-file-pdf" style="margin-right: 0.4rem;"></i> PDF
                    </a>
                  {% endif %}
                  
                  {% if talk.slides %}
                    <a href="{{ talk.slides | relative_url }}" target="_blank" class="btn btn-sm z-depth-0" role="button" style="font-size: 0.75rem; margin-left: 0.5rem;">
                      <i class="fas fa-chalkboard-teacher"></i> Slides
                    </a>
                  {% endif %}
                  
                  {% if talk.video %}
                    <a href="{{ talk.video }}" target="_blank" class="btn btn-sm z-depth-0" role="button" style="font-size: 0.75rem; margin-left: 0.5rem;">
                      <i class="fas fa-video"></i> Video
                    </a>
                  {% endif %}
                </div>
              </div>
            </td>
          </tr>
        {% endfor %}
      </table>
    </div>
  {% else %}
    <p>No talks yet...</p>
  {% endif %}
</div>
