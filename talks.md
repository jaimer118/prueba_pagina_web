---
title: "Talks & Seminars"
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

  /* Estilos para las etiquetas de estado */
  .status-badge {
    display: inline-block;
    font-size: 0.75rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    padding: 0.2rem 0.6rem;
    border-radius: 4px;
    margin-bottom: 0.5rem;
  }
  .status-badge--upcoming {
    background-color: #f2b200;
    color: #ffffff;
  }
  .status-badge--recorded {
    background-color: #e5e7eb;
    color: #4b5563;
  }
</style>

Explore past recordings and register for upcoming seminars organized by *Fusion EP Talks*.

<div style="display: flex; flex-direction: column; gap: 2.5rem; margin-top: 2rem; width: 100%;">
{% for post in site.posts %}
  <div style="display: flex; flex-wrap: wrap; gap: 2.5rem; align-items: center; border-bottom: 1px solid #eaeaea; padding-bottom: 2rem; width: 100%;">
    
    <!-- Miniatura Teaser -->
    {% if post.header.teaser %}
      <div style="flex: 0 0 300px; max-width: 100%;">
        <a href="{{ post.url | relative_url }}">
          <img src="{{ post.header.teaser | relative_url }}" alt="{{ post.title }}" style="width: 100%; border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.08); object-fit: cover; aspect-ratio: 16/9; display: block;">
        </a>
      </div>
    {% endif %}

    <!-- Contenido y Metadatos Dinámicos -->
    <div style="flex: 1 1 350px;">
      
      <!-- Lógica de Estado: Upcoming vs Recorded -->
      {% if post.youtube_id %}
        <span class="status-badge status-badge--recorded">Recorded</span>
      {% else %}
        <span class="status-badge status-badge--upcoming">Upcoming</span>
      {% endif %}

      <h2 style="margin-top: 0; margin-bottom: 0.5rem; font-size: 1.45rem;">
        <a href="{{ post.url | relative_url }}" style="text-decoration: none;">{{ post.title }}</a>
      </h2>
      
      <p style="font-size: 0.95em; color: #666; margin-bottom: 0.8rem;">
        📅 {{ post.date | date: "%B %d, %Y" }}
        {% if post.speaker %}
          &nbsp;|&nbsp; 👤 {{ post.speaker }}
        {% endif %}
      </p>

      {% if post.excerpt %}
        <div style="margin-bottom: 1.2rem; font-size: 1em; line-height: 1.6;">
          {{ post.excerpt | markdownify }}
        </div>
      {% endif %}

      <!-- Botón dinámico según disponibilidad de grabación -->
      {% if post.youtube_id %}
        <a href="{{ post.url | relative_url }}" class="btn btn--primary">View Details & Recording</a>
      {% else %}
        <a href="{{ post.url | relative_url }}" class="btn btn--warning">Register & Details</a>
      {% endif %}

    </div>

  </div>
{% endfor %}
</div>
