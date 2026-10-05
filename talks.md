---
title: "Talks & Seminars"
layout: single
permalink: /talks/
classes: wide
author_profile: false
---

<style>
  /* Filter bar styling */
  .filter-container {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin: 1.5rem 0 2.5rem 0;
    padding-bottom: 1.5rem;
    border-bottom: 1px solid #e5e7eb;
  }

  .filter-btn {
    appearance: none;
    border: 1px solid #d1d5db;
    background-color: #ffffff;
    color: #374151;
    font-size: 0.85rem;
    font-weight: 600;
    padding: 0.4rem 0.9rem;
    border-radius: 9999px;
    cursor: pointer;
    transition: all 0.2s ease-in-out;
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

  /* Tag pills inside post cards */
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

  /* Talk card animation */
  .talk-card {
    display: flex;
    flex-wrap: wrap;
    gap: 2.5rem;
    align-items: center;
    border-bottom: 1px solid #eaeaea;
    padding-bottom: 2rem;
    width: 100%;
    transition: opacity 0.25s ease;
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

Explore recordings and register for upcoming seminars organized by *Fusion EP Talks*. Filter by topic or session type below.

<!-- Tag & Status Filter Buttons -->
<div class="filter-container" id="filter-bar">
  <button class="filter-btn active" data-filter="all">All Talks</button>
  <button class="filter-btn" data-filter="upcoming">🟢 Upcoming</button>
  <button class="filter-btn" data-filter="tokamaks">Tokamaks</button>
  <button class="filter-btn" data-filter="stellarators">Stellarators</button>
  <button class="filter-btn" data-filter="turbulence">Turbulence & Transport</button>
  <button class="filter-btn" data-filter="diagnostics">Diagnostics</button>
  <button class="filter-btn" data-filter="theory">Theory & Modeling</button>
</div>

<!-- Empty search notice -->
<div id="no-talks-message">
  <p>No seminars match the selected filter.</p>
</div>

<!-- List of Talks -->
<div id="talks-list" style="display: flex; flex-direction: column; gap: 2.5rem; width: 100%;">
{% for post in site.posts %}

  {% assign is_recorded = false %}
  {% if post.youtube_id %}
    {% assign is_recorded = true %}
  {% endif %}

  <!-- Join tags into a space-separated lowercase string for easy querying -->
  {% capture post_tags %}{% for tag in post.tags %}{{ tag | downcase }} {% endfor %}{% endcapture %}

  <div class="talk-card" 
       data-status="{% if is_recorded %}recorded{% else %}upcoming{% endif %}" 
       data-tags="{{ post_tags | strip }}">
    
    <!-- Teaser Image -->
    {% if post.header.teaser %}
      <div style="flex: 0 0 300px; max-width: 100%;">
        <a href="{{ post.url | relative_url }}">
          <img src="{{ post.header.teaser | relative_url }}" alt="{{ post.title }}" style="width: 100%; border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.08); object-fit: cover; aspect-ratio: 16/9; display: block;">
        </a>
      </div>
    {% endif %}

    <!-- Card Content -->
    <div style="flex: 1 1 350px;">
      
      <!-- Status Badge -->
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

      <!-- Topic Tags Display -->
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

<!-- Pure Vanilla JS for Instant Filtering -->
<script>
  document.addEventListener("DOMContentLoaded", function () {
    const filterButtons = document.querySelectorAll(".filter-btn");
    const talkCards = document.querySelectorAll(".talk-card");
    const noResultsMsg = document.getElementById("no-talks-message");

    filterButtons.forEach(button => {
      button.addEventListener("click", function () {
        // Toggle active button class
        filterButtons.forEach(btn => btn.classList.remove("active"));
        this.classList.add("active");

        const selectedFilter = this.getAttribute("data-filter").toLowerCase();
        let visibleCount = 0;

        talkCards.forEach(card => {
          const cardTags = card.getAttribute("data-tags") || "";
          const cardStatus = card.getAttribute("data-status") || "";

          let matches = false;

          if (selectedFilter === "all") {
            matches = true;
          } else if (selectedFilter === "upcoming" || selectedFilter === "recorded") {
            matches = (cardStatus === selectedFilter);
          } else {
            // Check if tag is present in the space-delimited string
            matches = cardTags.split(" ").includes(selectedFilter);
          }

          if (matches) {
            card.classList.remove("is-hidden");
            visibleCount++;
          } else {
            card.classList.add("is-hidden");
          }
        });

        // Display empty message if no talks match
        if (visibleCount === 0) {
          noResultsMsg.style.display = "block";
        } else {
          noResultsMsg.style.display = "none";
        }
      });
    });
  });
</script>
