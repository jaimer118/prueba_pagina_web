---
title: "Charlas y Seminarios"
layout: single
permalink: /talks/
author_profile: false
---

Consulta el catálogo de seminarios y sesiones organizadas por *Fusion EP Talks*.

<div style="display: flex; flex-direction: column; gap: 2rem; margin-top: 2rem;">
{% for post in site.posts %}
  <div style="display: flex; gap: 1.5rem; align-items: flex-start; border-bottom: 1px solid #eaeaea; padding-bottom: 1.5rem;">
  
    {% if post.header.teaser %}
      <div style="flex-shrink: 0; width: 180px;">
        <a href="{{ post.url | relative_url }}">
          <img src="{{ post.header.teaser | relative_url }}" alt="{{ post.title }}" style="width: 100%; border-radius: 6px; box-shadow: 0 2px 5px rgba(0,0,0,0.1); object-fit: cover;">
        </a>
      </div>
    {% endif %}

    <div style="flex-grow: 1;">
      <h3 style="margin-top: 0; margin-bottom: 0.5rem;">
        <a href="{{ post.url | relative_url }}" style="text-decoration: none;">{{ post.title }}</a>
      </h3>
      
      <p style="font-size: 0.9em; color: #666; margin-bottom: 0.8rem;">
        📅 {{ post.date | date: "%d de %B de %Y" }}
      </p>

      {% if post.excerpt %}
        <div style="margin-bottom: 1rem; font-size: 0.95em;">
          {{ post.excerpt | markdownify }}
        </div>
      {% endif %}

      <a href="{{ post.url | relative_url }}" class="btn btn--primary btn--small">Más detalles y registro</a>
    </div>

  </div>
{% endfor %}
</div>
