---
title: "Localized absorption of laser energy by magnetized plasma target"
date: 2023-04-11
categories:
  - talks
tags:
  - theory
  - simulation
header:
  teaser: /assets/images/charla_2.png
  og_image: /assets/images/charla_2.png
speaker: "Dra. Ayushi Vashistha"
affiliation: "Institute For Plasma Research, India"
youtube_id: "mKXY__lxD_c"

# ==============================================================================
# SLIDES CONFIGURATION:
# - With slides:    Uncomment the line below and set the local path or URL.
# - Without slides: Keep the line commented out (#) or delete it entirely.
# ==============================================================================
# slides_url: "https://ejemplo.com/diapositivas.pdf"

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
Laser plasma interaction studies have attracted a great deal of interest for both fundamental as well as applied interests. Now is an exciting time for these studies, with the recent advancements in the world’s most powerful lasers and intense magnetic fields in the laboratory. 

The interaction of laser with plasma, however, predominantly gives energy to electron species. Energy transfer to ions is mainly mediated by electrons. In this talk, I would describe a mechanism for localized absorption of laser energy directly into ion species of magnetized plasma target, without any mediatory role by electrons. These studies are conducted using Particle-In-Cell simulations. Our study shows a way to dump laser energy into plasma using ions, averting the generation of energetic electrons, and hence avoiding current-generated instabilities.
