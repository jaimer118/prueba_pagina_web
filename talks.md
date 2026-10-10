---
title: "Talks & Seminars"
layout: single
permalink: /talks/
classes: wide
author_profile: false
---

<style>
  /* Filter Container */
  .filter-wrapper {
    margin: 1.5rem 0 2.5rem 0;
    padding-bottom: 1.5rem;
    border-bottom: 1px solid #e5e7eb;
  }

  .primary-filters {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    gap: 0.6rem;
  }

  /* Base Filter Button */
  .filter-btn {
    appearance: none;
    border: 1px solid #d1d5db;
    background-color: #ffffff;
    color: #374151;
    font-size: 0.85rem;
    font-weight: 600;
    padding: 0.45rem 1rem;
    border-radius: 9999px;
    cursor: pointer;
    transition: all 0.2s ease-in-out;
    display: inline-flex;
    align-items: center;
    gap: 0.4rem;
  }

  .filter-btn:hover {
    border-color: #009639;
    color: #009639;
  }

  .filter-btn.active {
    background-color: #009639;
    border-color: #009639;
    color: #ffffff;
    box-shadow: 0 2px 4px rgba(0, 150, 57, 0.2);
  }

  /* Tag Drawer Toggle */
  .btn--toggle-tags {
    border-style: dashed;
    background-color: #f9fafb;
  }
  .btn--toggle-tags.open {
    background-color: #e5e7eb;
    border-color: #9ca3af;
    color: #111827;
  }

  /* Clear Button (hidden by default) */
  .btn--clear {
    display: none;
    background-color: #fee2e2;
    border-color: #fca5a5;
    color: #b91c1c;
    font-size: 0.8rem;
    padding: 0.35rem 0.8rem;
  }
  .btn--clear:hover {
    background-color: #fecaca;
    color: #991b1b;
    border-color: #f87171;
  }
  .btn--clear.visible {
    display: inline-flex;
  }

  /* Expandable Tag Drawer */
  .tag-drawer {
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.3s cubic-bezier(0.4, 0, 0.2, 1), opacity 0.25s ease, margin 0.25s ease;
    opacity: 0;
    margin-top: 0;
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    align-items: center;
    background: #f8f9fa;
    padding: 0 1rem;
    border-radius: 8px;
  }

  .tag-drawer.is-open {
    max-height: 250px;
    opacity: 1;
    margin-top: 1rem;
    padding: 0.85rem 1rem;
    border: 1px solid #e5e7eb;
  }

  /* Topic Tag Pills inside Drawer */
  .tag-pill {
    appearance: none;
    border: 1px solid #d1d5db;
    background: #ffffff;
    color: #4b5563;
    font-size: 0.8rem;
    font-weight: 500;
    padding: 0.3rem 0.75rem;
    border-radius: 6px;
    cursor: pointer;
    transition: all 0.15s ease;
    user-select: none;
  }

  .tag-pill:hover {
    border-color: #009639;
    color: #009639;
  }

  .tag-pill.active {
    background-color: #009639;
    border-color: #009639;
    color: #ffffff;
  }

  .tag-pill .tag-check {
    display: none;
    margin-left: 0.3rem;
  }
  .tag-pill.active .tag-check {
    display: inline;
  }

  /* Status Badges */
  .status-badge {
    display: inline-block;
    font-size: 0.75rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    padding: 0.2rem 0.6rem;
    border-radius: 4px;
    margin-bottom: 0.5rem;
  }
  .status-badge--upcoming {
    background-color: #f2b200;
    color: #ffffff;
  }
  .status-badge--recorded {
    background-color: #e5e7eb;
    color: #4b5563;
  }

  /* Post Card Tags */
  .post-tag {
    display: inline-block;
    font-size: 0.75rem;
    background-color: #f3f4f6;
    color: #4b5563;
    padding: 0.15rem 0.5rem;
    border-radius: 4px;
    margin-right: 0.35rem;
    margin-top: 0.35rem;
  }

  /* Talk Card Layout */
  .talk-card {
    display: flex;
    flex-wrap: wrap;
    gap: 2.5rem;
    align-items: center;
    border-bottom: 1px solid #eaeaea;
    padding-bottom: 2rem;
    width: 100%;
    transition: opacity 0.2s ease;
  }

  .talk-card.is-hidden {
    display: none !important;
  }

  #no-talks-message {
    display: none;
    text-align: center;
    padding: 3rem 1rem;
    color: #6b7280;
    font-size: 1.1rem;
  }
</style>

Explore recordings and register for upcoming seminars organized by *Fusion EP Talks*.

<div class="filter-wrapper">
  <!-- Primary Filter Bar -->
  <div class="primary-filters">
    <button class="filter-btn active" id="btn-all" data-status="all">All Talks</button>
    <button class="filter-btn" data-status="upcoming">🟢 Upcoming</button>
    <button class="filter-btn" data-status="recorded">Recorded</button>

    <!-- Expand / Collapse Tag Drawer -->
    <button class="filter-btn btn--toggle-tags" id="toggle-tags-btn" type="button">
      <span>🏷️ Filter by Topics</span>
      <span id="toggle-indicator">▾</span>
      <span id="active-tag-count" style="display:none; background:#009639; color:#fff; font-size:0.7rem; border-radius:9999px; padding:0.1rem 0.45rem; margin-left:0.2rem;">0</span>
    </button>

    <!-- Reset / Clear Everything -->
    <button class="filter-btn btn--clear" id="btn-clear" type="button">
      ✕ Clear filters
    </button>
  </div>

  <!-- Expandable Tag Drawer (Multi-select) -->
  <div class="tag-drawer" id="tag-drawer">
    <span style="font-size:0.8rem; font-weight:600; color:#6b7280; margin-right:0.5rem;">Select topics:</span>
    <button class="tag-pill" data-tag="tokamaks">Tokamaks <span class="tag-check">✓</span></button>
    <button class="tag-pill" data-tag="stellarators">Stellarators <span class="tag-check">✓</span></button>
    <button class="tag-pill" data-tag="turbulence">Turbulence & Transport <span class="tag-check">✓</span></button>
    <button class="tag-pill" data-tag="mhd">MHD & Stability <span class="tag-check">✓</span></button>
    <button class="tag-pill" data-tag="diagnostics">Diagnostics <span class="tag-check">✓</span></button>
    <button class="tag-pill" data-tag="theory">Theory & Modeling <span class="tag-check">✓</span></button>
    <button class="tag-pill" data-tag="materials">Materials & Divertor <span class="tag-check">✓</span></button>
  </div>
</div>

<!-- Empty Result Notice -->
<div id="no-talks-message">
  <p>No seminars match all selected criteria.</p>
</div>

<!-- List of Talks -->
<div id="talks-list" style="display: flex; flex-direction: column; gap: 2.5rem; width: 100%;">
{% for post in site.posts %}

  {% assign is_recorded = false %}
  {% if post.youtube_id %}
    {% assign is_recorded = true %}
  {% endif %}

  {% capture post_tags %}{% for tag in post.tags %}{{ tag | downcase }} {% endfor %}{% endcapture %}

  <div class="talk-card" 
       data-status="{% if is_recorded %}recorded{% else %}upcoming{% endif %}" 
       data-tags="{{ post_tags | strip }}">
    
    {% if post.header.teaser %}
      <div style="flex: 0 0 300px; max-width: 100%;">
        <a href="{{ post.url | relative_url }}">
          <img src="{{ post.header.teaser | relative_url }}" alt="{{ post.title }}" style="width: 100%; border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.08); object-fit: cover; aspect-ratio: 16/9; display: block;">
        </a>
      </div>
    {% endif %}

    <div style="flex: 1 1 350px;">
      {% if is_recorded %}
        <span class="status-badge status-badge--recorded">Recorded</span>
      {% else %}
        <span class="status-badge status-badge--upcoming">Upcoming</span>
      {% endif %}

      <h2 style="margin-top: 0; margin-bottom: 0.5rem; font-size: 1.45rem;">
        <a href="{{ post.url | relative_url }}" style="text-decoration: none;">{{ post.title }}</a>
      </h2>
      
      <p style="font-size: 0.95em; color: #666; margin-bottom: 0.6rem;">
        📅 {{ post.date | date: "%B %d, %Y" }}
        {% if post.speaker %}
          &nbsp;|&nbsp; 👤 {{ post.speaker }}
        {% endif %}
      </p>

      {% if post.tags and post.tags.size > 0 %}
        <div style="margin-bottom: 0.8rem;">
          {% for tag in post.tags %}
            <span class="post-tag">#{{ tag }}</span>
          {% endfor %}
        </div>
      {% endif %}

      {% if post.excerpt %}
        <div style="margin-bottom: 1.2rem; font-size: 0.98em; line-height: 1.6; color: #4b5563;">
          {{ post.excerpt | markdownify }}
        </div>
      {% endif %}

      {% if is_recorded %}
        <a href="{{ post.url | relative_url }}" class="btn btn--primary">View Details & Recording</a>
      {% else %}
        <a href="{{ post.url | relative_url }}" class="btn btn--warning">Register & Details</a>
      {% endif %}

    </div>
  </div>
{% endfor %}
</div>

<!-- Multi-Select & Drawer Logic -->
<script>
  document.addEventListener("DOMContentLoaded", function () {
    const toggleBtn = document.getElementById("toggle-tags-btn");
    const toggleIndicator = document.getElementById("toggle-indicator");
    const tagDrawer = document.getElementById("tag-drawer");
    const tagCountBadge = document.getElementById("active-tag-count");
    const clearBtn = document.getElementById("btn-clear");
    const btnAll = document.getElementById("btn-all");

    const statusButtons = document.querySelectorAll("[data-status]");
    const tagPills = document.querySelectorAll(".tag-pill");
    const talkCards = document.querySelectorAll(".talk-card");
    const noResultsMsg = document.getElementById("no-talks-message");

    let currentStatus = "all";
    let activeTags = new Set();

    // 1. Toggle Drawer de etiquetas
    toggleBtn.addEventListener("click", function () {
      const isOpen = tagDrawer.classList.toggle("is-open");
      toggleBtn.classList.toggle("open", isOpen);
      toggleIndicator.textContent = isOpen ? "▴" : "▾";
    });

    // 2. Selección de Estado (All / Upcoming / Recorded)
    statusButtons.forEach(btn => {
      btn.addEventListener("click", function () {
        const selected = this.getAttribute("data-status");

        if (selected === "all") {
          resetAllFilters();
          return;
        }

        statusButtons.forEach(b => b.classList.remove("active"));
        this.classList.add("active");
        currentStatus = selected;
        btnAll.classList.remove("active");

        applyFilters();
      });
    });

    // 3. Multi-selección de tópicos
    tagPills.forEach(pill => {
      pill.addEventListener("click", function () {
        const tag = this.getAttribute("data-tag").toLowerCase();

        if (activeTags.has(tag)) {
          activeTags.delete(tag);
          this.classList.remove("active");
        } else {
          activeTags.add(tag);
          this.classList.add("active");
        }

        btnAll.classList.remove("active");
        updateDrawerBadge();
        applyFilters();
      });
    });

    // 4. Limpiar filtros
    clearBtn.addEventListener("click", resetAllFilters);

    function resetAllFilters() {
      currentStatus = "all";
      activeTags.clear();

      statusButtons.forEach(b => b.classList.remove("active"));
      btnAll.classList.add("active");

      tagPills.forEach(p => p.classList.remove("active"));

      // Cerrar cajón de tags si estaba abierto
      if (tagDrawer.classList.contains("is-open")) {
        tagDrawer.classList.remove("is-open");
        toggleBtn.classList.remove("open");
        toggleIndicator.textContent = "▾";
      }

      updateDrawerBadge();
      applyFilters();
    }

    function updateDrawerBadge() {
      const count = activeTags.size;
      if (count > 0) {
        tagCountBadge.textContent = count;
        tagCountBadge.style.display = "inline";
      } else {
        tagCountBadge.style.display = "none";
      }
    }

    // 5. Aplicar lógica de filtrado
    function applyFilters() {
      let visibleCount = 0;
      const isFiltered = currentStatus !== "all" || activeTags.size > 0;

      if (isFiltered) {
        clearBtn.classList.add("visible");
      } else {
        clearBtn.classList.remove("visible");
      }

      talkCards.forEach(card => {
        const cardStatus = card.getAttribute("data-status") || "";
        const rawCardTags = (card.getAttribute("data-tags") || "").split(" ").filter(Boolean);

        const matchesStatus = (currentStatus === "all" || cardStatus === currentStatus);

        let matchesTags = true;
        activeTags.forEach(tag => {
          if (!rawCardTags.includes(tag)) {
            matchesTags = false;
          }
        });

        if (matchesStatus && matchesTags) {
          card.classList.remove("is-hidden");
          visibleCount++;
        } else {
          card.classList.add("is-hidden");
        }
      });

      noResultsMsg.style.display = visibleCount === 0 ? "block" : "none";
    }

    // =========================================================================
    // 6. FIX BFCache: Reset forzoso cuando el usuario pulsa "Atrás" en el navegador
    // =========================================================================
    window.addEventListener("pageshow", function (event) {
      // event.persisted indica que la página se recuperó de la caché de navegación
      if (event.persisted) {
        resetAllFilters();
      }
    });
  });
</script>
