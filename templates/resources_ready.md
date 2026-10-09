---
title: "Computational Resources & Simulation Gallery"
layout: single
permalink: /resources/
classes: wide
author_profile: false
---

<style>
  /* Section switcher / tabs */
  .resource-nav {
    display: flex;
    gap: 1rem;
    margin: 1.5rem 0 2.5rem 0;
    border-bottom: 2px solid #e5e7eb;
    padding-bottom: 0.5rem;
  }
  .resource-nav-link {
    font-weight: 700;
    font-size: 1.05rem;
    color: #4b5563;
    text-decoration: none !important;
    padding: 0.5rem 0.8rem;
    border-radius: 6px;
    transition: all 0.2s;
  }
  .resource-nav-link:hover {
    color: #009639;
    background: #f3f4f6;
  }

  /* Grid layouts */
  .resource-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    gap: 2rem;
    margin-bottom: 3rem;
  }

  /* Code Workshop Cards */
  .workshop-card {
    background: #ffffff;
    border: 1px solid #e5e7eb;
    border-radius: 8px;
    padding: 1.5rem;
    box-shadow: 0 2px 6px rgba(0,0,0,0.04);
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    transition: transform 0.2s, box-shadow 0.2s;
  }
  .workshop-card:hover {
    transform: translateY(-2px);
    box-shadow: 0 6px 14px rgba(0,0,0,0.08);
  }

  .badge-lang {
    display: inline-block;
    font-size: 0.75rem;
    font-weight: 700;
    padding: 0.2rem 0.55rem;
    border-radius: 4px;
    background: #e0f2fe;
    color: #0369a1;
    text-transform: uppercase;
  }
  .badge-level {
    display: inline-block;
    font-size: 0.75rem;
    font-weight: 600;
    padding: 0.2rem 0.55rem;
    border-radius: 4px;
    background: #f3f4f6;
    color: #4b5563;
    margin-left: 0.4rem;
  }

  /* Visual Asset Card */
  .visual-card {
    background: #ffffff;
    border: 1px solid #e5e7eb;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 2px 6px rgba(0,0,0,0.04);
    display: flex;
    flex-direction: column;
  }
  .visual-media {
    width: 100%;
    background: #111827;
    display: flex;
    align-items: center;
    justify-content: center;
    max-height: 260px;
    overflow: hidden;
  }
  .visual-media img,
  .visual-media video {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  .visual-body {
    padding: 1.25rem;
    display: flex;
    flex-direction: column;
    flex: 1;
    justify-content: space-between;
  }

  .code-drawer {
    background: #f9fafb;
    border-top: 1px solid #e5e7eb;
    padding: 0.75rem 1.25rem;
    font-size: 0.85rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
</style>

<div class="resource-nav">
  <a href="#workshops" class="resource-nav-link">💻 Interactive Code Notebooks</a>
  <a href="#gallery" class="resource-nav-link">🎬 Simulation & Animation Gallery</a>
</div>

<p>
  Welcome to the open computational repository of <strong>Fusion EP Talks</strong>. Here you will find hands-on numerical tutorials, educational code notebooks with one-click cloud execution, and high-resolution plasma physics simulations accompanied by their reproducible source code.
</p>

---

<h2 id="workshops" style="margin-top: 2rem;">
  💻 Interactive Code Notebooks & Tutorials
</h2>
<p style="color: #6b7280; font-size: 0.95rem; margin-bottom: 1.5rem;">
  Run directly in your browser with zero local installation using Google Colab, or clone the repository to run locally.
</p>

<div class="resource-grid">

  <!-- Card 1 -->
  <div class="workshop-card">
    <div>
      <div style="margin-bottom: 0.75rem;">
        <span class="badge-lang">Python</span>
        <span class="badge-level">Introductory</span>
      </div>
      <h3 style="margin: 0 0 0.5rem 0; font-size: 1.25rem;">1D Heat Diffusion & Transport Solver</h3>
      <p style="font-size: 0.9rem; color: #4b5563; line-height: 1.5;">
        Solves the 1D cylindrical heat conduction equation with realistic boundary conditions and localized central auxiliary heating, demonstrating thermal equilibrium timescales in magnetic confinement.
      </p>
    </div>
    <div style="margin-top: 1.2rem; display: flex; gap: 0.6rem; flex-wrap: wrap;">
      <a href="https://colab.research.google.com" target="_blank" rel="noopener noreferrer" class="btn btn--primary" style="margin: 0; font-size: 0.8rem; padding: 0.4rem 0.8rem;">
        <i class="fas fa-play"></i> Run in Colab
      </a>
      <a href="https://github.com" target="_blank" rel="noopener noreferrer" class="btn btn--inverse" style="margin: 0; font-size: 0.8rem; padding: 0.4rem 0.8rem;">
        <i class="fab fa-github"></i> Repository
      </a>
    </div>
  </div>

  <!-- Card 2 -->
  <div class="workshop-card">
    <div>
      <div style="margin-bottom: 0.75rem;">
        <span class="badge-lang">Python</span>
        <span class="badge-level">Intermediate</span>
      </div>
      <h3 style="margin: 0 0 0.5rem 0; font-size: 1.25rem;">Guiding-Center Drift Integrator</h3>
      <p style="font-size: 0.9rem; color: #4b5563; line-height: 1.5;">
        Integrates guiding-center equations of motion in toroidal magnetic geometry with $\nabla B$ and curvature drifts. Visualizes passing and trapped banana orbits in tokamaks.
      </p>
    </div>
    <div style="margin-top: 1.2rem; display: flex; gap: 0.6rem; flex-wrap: wrap;">
      <a href="https://colab.research.google.com" target="_blank" rel="noopener noreferrer" class="btn btn--primary" style="margin: 0; font-size: 0.8rem; padding: 0.4rem 0.8rem;">
        <i class="fas fa-play"></i> Run in Colab
      </a>
      <a href="https://github.com" target="_blank" rel="noopener noreferrer" class="btn btn--inverse" style="margin: 0; font-size: 0.8rem; padding: 0.4rem 0.8rem;">
        <i class="fab fa-github"></i> Repository
      </a>
    </div>
  </div>

  <!-- Card 3 -->
  <div class="workshop-card">
    <div>
      <div style="margin-bottom: 0.75rem;">
        <span class="badge-lang">Julia</span>
        <span class="badge-level">Advanced</span>
      </div>
      <h3 style="margin: 0 0 0.5rem 0; font-size: 1.25rem;">Toy 2D Electrostatic Turbulence (Hasegawa-Wakatani)</h3>
      <p style="font-size: 0.9rem; color: #4b5563; line-height: 1.5;">
        Pseudospectral solver simulating drift-wave turbulence and zonal flow self-organization in magnetized edge plasmas using the Hasegawa-Wakatani model.
      </p>
    </div>
    <div style="margin-top: 1.2rem; display: flex; gap: 0.6rem; flex-wrap: wrap;">
      <a href="https://github.com" target="_blank" rel="noopener noreferrer" class="btn btn--inverse" style="margin: 0; font-size: 0.8rem; padding: 0.4rem 0.8rem;">
        <i class="fab fa-github"></i> View on GitHub
      </a>
    </div>
  </div>

</div>

---

<h2 id="gallery" style="margin-top: 2.5rem;">
  🎬 Simulation & Animation Gallery
</h2>
<p style="color: #6b7280; font-size: 0.95rem; margin-bottom: 1.5rem;">
  Scientific assets generated for workshops and seminar companion materials. You are free to reuse these animations in academic presentations or theses under <strong>CC BY 4.0</strong> attribution.
</p>

<div class="resource-grid">

  {% for visual in site.data.resources_visuals %}
  <div class="visual-card">
    <div class="visual-media">
      {% if visual.media_type == "video" %}
        <video controls playsinline preload="metadata" poster="{{ visual.poster_url | relative_url }}">
          <source src="{{ visual.media_url }}" type="video/mp4">
          Your browser does not support the video tag.
        </video>
      {% else %}
        <img src="{{ visual.media_url | relative_url }}" alt="{{ visual.title }}" loading="lazy">
      {% endif %}
    </div>

    <div class="visual-body">
      <div>
        <span style="font-size: 0.75rem; font-weight: 700; color: #009639; text-transform: uppercase;">
          {{ visual.category }}
        </span>
        <h3 style="margin: 0.3rem 0 0.5rem 0; font-size: 1.15rem;">{{ visual.title }}</h3>
        <p style="font-size: 0.88rem; color: #4b5563; line-height: 1.5; margin-bottom: 0.75rem;">
          {{ visual.description }}
        </p>
      </div>

      <div style="font-size: 0.8rem; color: #6b7280; background: #f3f4f6; padding: 0.5rem 0.75rem; border-radius: 4px; margin-top: 0.5rem;">
        <strong>Cite:</strong> <em>{{ visual.citation }}</em>
      </div>
    </div>

    <div class="code-drawer">
      <span style="font-weight: 600; color: #374151;">
        <i class="fas fa-code"></i> {{ visual.language }}
      </span>
      <a href="{{ visual.code_repo }}" target="_blank" rel="noopener noreferrer" style="font-weight: 600; color: #009639; text-decoration: underline;">
        Get Source Script &rarr;
      </a>
    </div>
  </div>
  {% endfor %}

</div>

> **Contribute Code or Visuals:** Have you developed an educational simulation or high-resolution animation you would like to share with the community? Submit your notebook or visualization through our [Contact page]({{ '/contact/' | relative_url }}).
