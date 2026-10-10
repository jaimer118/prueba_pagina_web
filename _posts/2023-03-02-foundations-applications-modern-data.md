---
title: "Foundations & applications of modern data science in fusion"
date: 2023-03-02
categories:
  - talks
tags:
  - fusion
  - plasma-physics
header:
  teaser: /assets/images/talks_teaser/geert_foundation.png
speaker: "Dr. Geert Verdoolaege"
affiliation: "Ghent University, Belgium"
youtube_id: "2RmqyLCLHSY"

# ==============================================================================
# SLIDES CONFIGURATION:
# - With slides:    Uncomment the line below and set the local path or URL.
# - Without slides: Keep the line commented out (#) or delete it entirely.
# ==============================================================================
# slides_url: "/assets/slides/presentation.pdf"

author_profile: false
---

**Speaker:** {{ page.speaker }}  
**Position & Institution:** {{ page.affiliation }}  
**Date:** {{ page.date | date: "%B %d, %Y" }}  
{% if page.slides_url %}
**Slides:** [Download Presentation (PDF)]({{ page.slides_url | relative_url }}){: .btn .btn--info .btn--small target="_blank" rel="noopener noreferrer"}  
{% endif %}

<div style="clear: both; margin-top: 1.5rem;"></div>

{% if page.youtube_id %}
### Recording

{% include video id=page.youtube_id provider="youtube" %}

<p style="text-align: center; margin-top: 1.25rem; display: flex; justify-content: center; gap: 0.75rem; flex-wrap: wrap;">
  <a href="https://www.youtube.com/watch?v={{ page.youtube_id }}" target="_blank" rel="noopener noreferrer" class="btn btn--primary">
    <i class="fab fa-youtube"></i> Watch on YouTube
  </a>
  {% if page.slides_url %}
  <a href="{{ page.slides_url | relative_url }}" target="_blank" rel="noopener noreferrer" class="btn btn--inverse">
    <i class="fas fa-file-pdf"></i> Download Slides (PDF)
  </a>
  {% endif %}
</p>
{% endif %}

---

### Abstract
In parallel with a similar evolution in society at large, modern data science is making an increasingly significant impact on the worldwide activities for the development of fusion energy. A fusion device is a source of lots of complex data, not only from plasma diagnostics, but also from a host of sensors that monitor various machine subsystems and components. Analysis of these data, possibly from multiple devices and supplemented with data from plasma modeling, requires adequate techniques from statistics and (Bayesian) probability, in order to cope with the various sources of uncertainty. Recent machine learning techniques also have begun to make their appearance in many applications in fusion, including pattern recognition, prediction and anomaly detection. In this talk, I will first discuss the foundations of data science allowing this type of analysis. I will then present a number of recent applications, such as robust estimation of scaling laws, probabilistic characterization of plasma instabilities, sensor fusion and predictive maintenance in a fusion device.

