---
title: "Foundations & applications of modern data science in fusion"
date: 2023-05-30
categories:
  - talks
tags:
  - fusion
  - plasma-physics
header:
  teaser: /assets/images/talks_teaser/guangming_zhou.png
speaker: "Dr. Guangming Zhou"
affiliation: "Karlsruhe Institute of Technology, Germany"
youtube_id: "ZGmc8yGXeL0"

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
In any Deuterium-Tritium fusion power plant, deuterium and tritium are the essential fuels. Deuterium is of great abundance and easy to recover from the seawater. On the other hand, tritium is radioactive and very scarce in nature. In the D-T fusion power plant, tritium has to be produced in the so-called breeding blanket, a component that is surrounding the plasma like a blanket. Breeding blanket has three main functions: tritium breeding, high-grade heat extraction and nuclear shielding. In Europe, there are two candidates of breeding blanket concepts that are being considered for the European DEMO power plant: the Helium Cooled Pebble Bed – HCPB and the Water Cooled Lithium Lead – WCLL. In this talk, the status of the design and R&D activities of the HCPB breeding blanket will be presented. This talk concludes with outlook and future activities.
