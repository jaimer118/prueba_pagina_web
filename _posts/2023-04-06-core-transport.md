---
title: "Integrated core transport modeling of NSTX plasmas using the OMFIT workflow"
date: 2023-04-06
categories:
  - talks
tags:
  - tokamaks
  - transport
  - simulation
header:
  teaser: /assets/images/charla.png
  og_image: /assets/images/charla.png
speaker: "Dra. Galina Avdeeva"
affiliation: "Oak Ridge Associated Universities (General Atomics)"
youtube_id: "JwrlB9ZOPjc"

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
{% if page.slides_url and page.slides_url != "" %}
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
  {% if page.slides_url and page.slides_url != "" %}
  <a href="{{ page.slides_url | relative_url }}" target="_blank" rel="noopener noreferrer" class="btn btn--inverse">
    <i class="fas fa-file-pdf"></i> Download Slides (PDF)
  </a>
  {% endif %}
</p>
{% endif %}

---

### Abstract
A numerical plasma modeling provides the most accurate representation of the experimental reality when various models are integrated in a way that enables the determination of the most consistent solution. The OMFIT framework provides a convenient user-friendly interface to combine various codes into an integrated workflow with opportunities for the device specification, many options of data visualization and modeling/experiment comparison.

In this work, such a workflow: from an equilibrium reconstruction to the plasma profiles prediction will be demonstrated in applications to a heat plasma transport study on the low aspect ratio NSTX tokamak. Spherical tokamaks are one of the leading concepts for the design of future fusion power pilot plants and the analysis of NSTX plasma helps to determine the optimal aspect ratio for a next-step fusion facility.
