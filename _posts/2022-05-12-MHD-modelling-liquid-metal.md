---
title: "Magnetohydrodynamic modelling for liquid metal systems and components"
date: 2022-05-12
categories:
  - talks
tags:
  - fusion
  - plasma-physics
header:
  teaser: /assets/images/talks_teaser/alessandro_tassone.png
speaker: "Dr. Alessandro Tassone"
affiliation: "Sapienza University of Rome, Italy"
youtube_id: "ZPx3byW_Yjk"

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
Liquid metals are promising fluids for applications in breeding blankets (BB) and plasma facing components (PFC) but, owing to their high electrical conductivity, tend to behave in bizarre and counter-intuitive ways when exposed to the intense magnetic fields which are typical of magnetic confinement reactors. Comprehension and characterization of the magnetohydrodynamic (MHD) phenomena is necessary to successfully develop and deploy components based on liquid metal technology. In this contribution, the most relevant effects of MHD for BB and PFC are reviewed and the work done at Sapienza University of Rome to model these phenomena is presented. The focus will be on direct numerical simulations performed with computational fluid-dynamic codes and the establishment of a framework for a system level code to be used in the future for safety analyses.
