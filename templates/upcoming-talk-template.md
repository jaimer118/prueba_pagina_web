---
title: "Full Title of the Upcoming Seminar or Talk"
date: 2026-11-20
categories:
  - talks
tags:
  - fusion
  - plasma-physics
header:
  teaser: /assets/images/charlas/talk-poster.png
speaker: "Dr. Full Name"
affiliation: "Research Institution / University"
start_time: "16:00"
end_time: "17:00"
time_display: "16:00 - 17:00 CET"
platform: "Online via Zoom"
registration_url: "https://zoom.us/webinar/register/example-link"
author_profile: false
---

**Speaker:** {{ page.speaker }}  
**Position & Institution:** {{ page.affiliation }}  
**Date & Time:** {{ page.date | date: "%B %d, %Y" }} at {{ page.time }}  
**Platform:** {{ page.platform }}  

<div style="clear: both; margin-top: 1.5rem;"></div>

### Registration
Join us live for this upcoming session. Registration is completely free and open to students, researchers, and anyone interested in fusion science.

<p style="text-align: center; margin: 1.5rem 0;">
  <a href="{{ page.registration_url }}" target="_blank" rel="noopener noreferrer" class="btn btn--warning btn--large">
    Register to Attend
  </a>
</p>

<!-- Calendar Dropdown Button -->
{% include add-to-calendar.html 
   title=page.title 
   start_time=page.start_time 
   end_time=page.end_time 
   platform=page.platform 
%}

> **Note:** The full video recording and presentation slides will be published on this page shortly after the live session.

---

### Abstract
Insert the general overview of the seminar here, presenting the scientific background and the relevance of the topic within magnetic confinement fusion or plasma physics.

Detail in this second paragraph the core methodology, experimental apparatus, numerical modeling, or simulation frameworks discussed during the presentation.
