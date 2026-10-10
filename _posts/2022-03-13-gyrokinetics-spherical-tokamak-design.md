---
title: "Using gyrokinetics to inform spherical tokamak power plant design"
date: 2022-03-13
categories:
  - talks
tags:
  - fusion
  - plasma-physics
header:
  teaser: /assets/images/talks_teaser/robert_davies.png
speaker: "Dr. Robert Davies"
affiliation: "Max Planck Institute for Plasma Physics, Greifswald, Germany"
youtube_id: "yo4zeWQNTvs"

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
Now is an exciting time for magnetic confinement fusion, with a great deal of private and public interest in a variety of reactor concepts. However, a major consideration for the design and operation of commercially viable fusion power plants is plasma turbulence, which constrains the energy confinement, density and temperature in the plasma. In this talk, I describe how plasma turbulence (and the spatially small instabilities which drive it, called "microinstabilities") can be simulated using gyrokinetic codes. These simulations can be used to understand and predict experimental results, but also to assess the viability of hypothetical fusion plasmas. In this way, gyrokinetics can be used to influence reactor design. As a specific example of this, I describe how a particular microinstability (the "kinetic ballooning mode") provides a constraint on the plasma shape for commercially viable spherical tokamak (ST) power plants.
