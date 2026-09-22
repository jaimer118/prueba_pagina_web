---
title: "Talks"
layout: single
permalink: /talks/
classes: wide
author_profile: false
---

<style>
  
  .page {
    width: 100% !important;
    padding-right: 0 !important;
    float: none !important;
  }
  .page__inner-wrap {
    width: 100% !important;
    max-width: 100% !important;
    float: none !important;
  }
  .page__content {
    width: 100% !important;
    max-width: 100% !important;
  }
</style>

Consulta el catálogo de seminarios y sesiones organizadas por *Fusion EP Talks*.

<div style="display: flex; flex-direction: column; gap: 2.5rem; margin-top: 2rem; width: 100%;">
{% for post in site.posts %}
  <div style="display: flex; flex-wrap: wrap; gap: 2.5rem; align-items: center; border-bottom: 1px solid #eaeaea; padding-bottom: 2rem; width: 100%;">
    
    
    {% if post.header.teaser %}
      <div style="flex: 0 0 320px; max-width: 100%;">
        <a href="{{ post.url | relative_url }}">
          <img src="{{ post.header.teaser | relative_url }}" alt="{{ post.title }}" style="width: 100%; border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.08); object-fit: cover; aspect-ratio: 16/9; display: block;">
        </a>
      </div>
    {% endif %}

    
    <div style="flex: 1 1 350px;">
      <h2 style="margin-top: 0; margin-bottom: 0.5rem; font-size: 1.5rem;">
        <a href="{{ post.url | relative_url }}" style="text-decoration: none;">{{ post.title }}</a>
      </h2>
      
      <p style="font-size: 0.95em; color: #666; margin-bottom: 0.8rem;">
        📅 {{ post.date | date: "%d de %B de %Y" }}
      </p>

      {% if post.excerpt %}
        <div style="margin-bottom: 1.2rem; font-size: 1em; line-height: 1.6;">
          {{ post.excerpt | markdownify }}
        </div>
      {% endif %}

      <a href="{{ post.url | relative_url }}" class="btn btn--primary">Más detalles y registro</a>
    </div>

  </div>
{% endfor %}
</div>
