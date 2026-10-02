---
title: "Full Title of the Recorded Seminar"
date: 2026-10-15
categories:
  - talks
tags:
  - fusion
  - plasma-physics
header:
  teaser: /assets/images/charlas/talk-poster.png
speaker: "Dr. Full Name"
affiliation: "Research Institution / University"
youtube_id: "JwrlB9ZOPjc"
slides_url: "/assets/slides/presentation.pdf"
author_profile: false
---

**Speaker:** {{ page.speaker }}  
**Position & Institution:** {{ page.affiliation }}  
**Date:** {{ page.date | date: "%B %d, %Y" }}  
{% if page.slides_url %}
**Slides:** [Download Presentation (PDF)]({{ page.slides_url | relative_url }}){: .btn .btn--info .btn--small target="_blank" rel="noopener noreferrer"}  
{% endif %}

<div style="clear: both; margin-top: 1.5rem;"></div>

### Recording

{% include video id=page.youtube_id provider="youtube" %}

<p style="text-align: center; margin-top: 1rem;">
  <a href="https://www.youtube.com/watch?v={{ page.youtube_id }}" target="_blank" rel="noopener noreferrer" class="btn btn--primary btn--large">
    <i class="fab fa-youtube"></i> Open directly on YouTube
  </a>
</p>

---

### Abstract
Summary of the presentation, covering theoretical foundations, key simulation benchmarks, or experimental diagnostic findings.

Outline here the main conclusions and future research outlook presented during the session.
