---
title: "Opportunities: Degrees, PhDs & Internships"
layout: single
permalink: /opportunities/
classes: wide
author_profile: false
---

<style>
  /* Filter bar */
  .opp-filter-bar {
    display: flex;
    flex-wrap: wrap;
    gap: 0.6rem;
    margin: 1.5rem 0 2.5rem 0;
    padding-bottom: 1.25rem;
    border-bottom: 1px solid #e5e7eb;
  }

  .opp-filter-btn {
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
  }

  .opp-filter-btn:hover {
    border-color: #009639;
    color: #009639;
  }

  .opp-filter-btn.active {
    background-color: #009639;
    border-color: #009639;
    color: #ffffff;
    box-shadow: 0 2px 4px rgba(0, 150, 57, 0.2);
  }

  /* Grid of Opportunities */
  .opp-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
    gap: 1.5rem;
    margin-bottom: 3rem;
  }

  .opp-card {
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

  .opp-card:hover {
    transform: translateY(-2px);
    box-shadow: 0 6px 14px rgba(0,0,0,0.08);
  }

  .opp-card.is-hidden {
    display: none !important;
  }

  /* Track Badges */
  .badge-track {
    display: inline-block;
    font-size: 0.75rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    padding: 0.2rem 0.55rem;
    border-radius: 4px;
    margin-bottom: 0.5rem;
  }
  .badge-track--master { background-color: #dbeafe; color: #1e40af; }
  .badge-track--phd { background-color: #dcfce7; color: #15803d; }
  .badge-track--school, .badge-track--internship { background-color: #fef3c7; color: #b45309; }

  /* Deadline indicator */
  .deadline-tag {
    font-size: 0.8rem;
    font-weight: 600;
    color: #b91c1c;
    background: #fee2e2;
    padding: 0.2rem 0.6rem;
    border-radius: 4px;
    display: inline-flex;
    align-items: center;
    gap: 0.3rem;
  }
  .deadline-tag--ongoing {
    color: #047857;
    background: #d1fae5;
  }

  /* Submission callout */
  .submit-callout {
    background: #f9fafb;
    border-left: 4px solid #009639;
    border-radius: 6px;
    padding: 1.25rem 1.5rem;
    margin: 2rem 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 1rem;
  }
</style>

Discover academic pathways in nuclear fusion and plasma physics, including European master's degrees, funded PhD vacancies, summer schools, and research grants.

<div class="submit-callout">
  <div>
    <h4 style="margin: 0 0 0.3rem 0; font-size: 1.05rem; color: #1f2937;">Are you recruiting students or researchers?</h4>
    <p style="margin: 0; font-size: 0.9rem; color: #4b5563;">
      Post your Master's, PhD vacancy, or summer school announcement directly to our community board.
    </p>
  </div>
  <a href="{{ '/contact/' | relative_url }}" class="btn btn--primary" style="margin: 0; font-size: 0.85rem;">
    Submit an Opportunity
  </a>
</div>

<!-- Category Filters -->
<div class="opp-filter-bar">
  <button class="opp-filter-btn active" data-filter="all">All Tracks</button>
  <button class="opp-filter-btn" data-filter="master">🎓 Master's Programmes</button>
  <button class="opp-filter-btn" data-filter="phd">🔬 PhD Positions</button>
  <button class="opp-filter-btn" data-filter="school">☀️ Summer Schools & Internships</button>
</div>

<!-- Convert current build date to an integer YYYYMMDD for numerical comparison -->
{% assign today_int = site.time | date: "%Y%m%d" | plus: 0 %}

<h2>Active Calls & Degree Programmes</h2>

<div class="opp-grid" id="opps-container">

  {% for item in site.data.opportunities %}
    {% assign show_item = false %}
    {% if item.deadline == "ongoing" %}
      {% assign show_item = true %}
    {% else %}
      {% assign item_deadline_int = item.deadline | date: "%Y%m%d" | plus: 0 %}
      {% if item_deadline_int >= today_int %}
        {% assign show_item = true %}
      {% endif %}
    {% endif %}

    {% if show_item %}
    <div class="opp-card" data-track="{{ item.type }}">
      <div>
        <!-- Track badge -->
        <span class="badge-track badge-track--{{ item.type }}">
          {% if item.type == "master" %}Master's Degree
          {% elsif item.type == "phd" %}PhD Position
          {% else %}Summer School / Grant{% endif %}
        </span>

        <h3 style="margin: 0.4rem 0 0.5rem 0; font-size: 1.2rem; color: #111827;">{{ item.title }}</h3>
        
        <p style="font-size: 0.88rem; color: #4b5563; margin-bottom: 0.4rem;">
          🏛️ <strong>{{ item.institution }}</strong>
        </p>
        <p style="font-size: 0.85rem; color: #6b7280; margin-bottom: 0.9rem;">
          📍 {{ item.location }}
        </p>

        <p style="font-size: 0.9rem; color: #374151; line-height: 1.5; margin-bottom: 1rem;">
          {{ item.description }}
        </p>
      </div>

      <div>
        <div style="margin-bottom: 1rem;">
          {% if item.deadline == "ongoing" %}
            <span class="deadline-tag deadline-tag--ongoing">📅 Rolling / Ongoing</span>
          {% else %}
            <span class="deadline-tag">📅 Deadline: {{ item.deadline | date: "%B %d, %Y" }}</span>
          {% endif %}
        </div>

        {% if item.funding %}
          <p style="font-size: 0.82rem; color: #047857; margin-bottom: 1rem; font-weight: 500;">
            💶 {{ item.funding }}
          </p>
        {% endif %}

        <a href="{{ item.link }}" target="_blank" rel="noopener noreferrer" class="btn btn--inverse" style="width: 100%; text-align: center; margin: 0;">
          Official Details & Apply &rarr;
        </a>
      </div>
    </div>
    {% endif %}
  {% endfor %}

</div>

<!-- Collapsible Archive for Expired Calls -->
<details style="margin-top: 3rem; background: #f9fafb; border: 1px solid #e5e7eb; border-radius: 8px; padding: 1rem 1.25rem;">
  <summary style="font-weight: 600; color: #4b5563; cursor: pointer;">
    📁 View Recently Closed / Historical Positions
  </summary>
  <div style="margin-top: 1rem;">
    <ul>
      {% for item in site.data.opportunities %}
        {% if item.deadline != "ongoing" %}
          {% assign item_deadline_int = item.deadline | date: "%Y%m%d" | plus: 0 %}
          {% if item_deadline_int < today_int %}
            <li style="margin-bottom: 0.5rem; font-size: 0.9rem; color: #6b7280;">
              <strong>{{ item.title }}</strong> – {{ item.institution }} (Closed: {{ item.deadline | date: "%B %d, %Y" }})
            </li>
          {% endif %}
        {% endif %}
      {% endfor %}
    </ul>
  </div>
</details>

<!-- Track Filtering Script -->
<script>
  document.addEventListener("DOMContentLoaded", function () {
    const filterBtns = document.querySelectorAll(".opp-filter-btn");
    const cards = document.querySelectorAll(".opp-card");

    filterBtns.forEach(btn => {
      btn.addEventListener("click", function () {
        filterBtns.forEach(b => b.classList.remove("active"));
        this.classList.add("active");

        const selectedTrack = this.getAttribute("data-filter");

        cards.forEach(card => {
          const track = card.getAttribute("data-track");

          if (selectedTrack === "all") {
            card.classList.remove("is-hidden");
          } else if (selectedTrack === "school") {
            // Group summer schools and internships together
            if (track === "school" || track === "internship") {
              card.classList.remove("is-hidden");
            } else {
              card.classList.add("is-hidden");
            }
          } else {
            if (track === selectedTrack) {
              card.classList.remove("is-hidden");
            } else {
              card.classList.add("is-hidden");
            }
          }
        });
      });
    });
  });
</script>
