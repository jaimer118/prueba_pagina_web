---
title: "Molecular plasma spectroscopy in JET tokamak"
date: 2023-03-07
categories:
  - talks
tags:
  - fusion
  - plasma-physics
header:
  teaser: /assets/images/talks_teaser/ewa_pawelec.png
speaker: "Prof. Dr. Ewa Pawelec"
affiliation: "University of Opole, Poland"
youtube_id: "7i1J9x0TcBQ"

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
Magnetic confinement fusion ordinarily is not connected with molecular spectroscopy, because most of the interest is directed at the hot core and confining pedestal. Nevertheless, the plasma spreads out of those regions and, at certain point touches the walls, so at in this region it is, by every measure, a low-temperature, if certainly very specific plasma. In the regions close enough to the vessel walls, the nearly-total ionization of the core and pedestal regions is not present anymore, and atoms, molecules and molecular ions strongly contribute to the overall mixture. Their presence influences both the overall plasma behavior and the vessel walls erosion, which contributes to the impurities permeating the pedestal and core plasma. Most important molecules in the magnetic confinement fusion are the hydrogen-containing ones, from the hydrogenic species in different isotopic combinations (H2, D2, T2 and mixed) to all kinds of hydride, created where the hydrogenic plasma encounters other elements. Those other elements can be present in the walls, such as beryllium, tungsten, boron or carbon, or be one of the seeded impurities, like nitrogen. In those reactions different hydrides may be created. Most important are the metallic hydrides, especially BeH/D/T, which contribute to the wall erosion by a process called CAPS (Chemical Assisted Physical Sputtering), which is also a process which may be detrimental both to the walls and to the pedestal and core plasma. The hydrogenic molecules are very important e.g. in the behavior of the divertor, where the detachment conditions are strongly affected by molecular processes. Spectroscopic study of molecules is not simple, because the spectra are complex, but on the other hand, it provides data on the creation process of the light-emitting molecular states. 

In this presentation, examples of the spectra and their analyses will be taken from JET experiments and comprise different isotopologues of hydrogen molecule and beryllium and nitrogen hydride. It will also be shown how those results contribute to better understanding of different processes happening in the low-temperature regions of the magnetic confinement fusion plasma.
