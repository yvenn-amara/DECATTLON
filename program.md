---
layout: default
title: Program
description: Detailed program for the two days of the workshop.
---

<div class="page-hero">
  <div class="container">
    <p class="page-kicker">Workshop — November 3–4, 2026</p>
    <h1>Program</h1>
    <p class="lead">Two days of plenary sessions, workshops, round tables, and poster presentations on transfer learning and foundation models.</p>
  </div>
</div>

<section class="section">
  <div class="container">

    <!-- TABS -->
    <div class="program-tabs" role="tablist" aria-label="Workshop days">
      <button class="tab-btn is-active" role="tab" aria-selected="true"  aria-controls="day1" id="tab-day1">Day 1 — Tuesday, Nov 3</button>
      <button class="tab-btn"           role="tab" aria-selected="false" aria-controls="day2" id="tab-day2">Day 2 — Wednesday, Nov 4</button>
    </div>

    <!-- DAY 1 -->
    <div id="day1" class="day-panel is-active" role="tabpanel" aria-labelledby="tab-day1">
      <p class="day-label">{{ site.data.program.day1.label }}</p>
      <div class="timeline">
        {% for session in site.data.program.day1.sessions %}
        {% assign type = session.type %}
        {% if type == "plenary" %}{% assign badge = "Plenary" %}
        {% elsif type == "session" %}{% assign badge = "Session" %}
        {% elsif type == "workshop" %}{% assign badge = "Workshop" %}
        {% elsif type == "poster" %}{% assign badge = "Posters" %}
        {% elsif type == "panel" %}{% assign badge = "Round table" %}
        {% elsif type == "social" %}{% assign badge = "Social" %}
        {% elsif type == "meal" %}{% assign badge = "Meal" %}
        {% else %}{% assign badge = "Break" %}
        {% endif %}
        <div class="timeline-item" data-type="{{ type }}">
          <div class="session-card">
            <div class="session-head">
              <span class="session-badge badge-{{ type }}">{{ badge }}</span>
              <span class="session-time">{{ session.time }}</span>
            </div>
            <p class="session-title">{{ session.title }}</p>
            {% if session.speakers %}
            <p class="session-speakers">
              {% for sp in session.speakers %}{{ sp }}{% unless forloop.last %}, {% endunless %}{% endfor %}
            </p>
            {% endif %}
            {% if session.description %}
            <p class="session-desc">{{ session.description }}</p>
            {% endif %}
          </div>
        </div>
        {% endfor %}
      </div>
    </div>

    <!-- DAY 2 -->
    <div id="day2" class="day-panel" role="tabpanel" aria-labelledby="tab-day2">
      <p class="day-label">{{ site.data.program.day2.label }}</p>
      <div class="timeline">
        {% for session in site.data.program.day2.sessions %}
        {% assign type = session.type %}
        {% if type == "plenary" %}{% assign badge = "Plenary" %}
        {% elsif type == "session" %}{% assign badge = "Session" %}
        {% elsif type == "workshop" %}{% assign badge = "Workshop" %}
        {% elsif type == "poster" %}{% assign badge = "Posters" %}
        {% elsif type == "panel" %}{% assign badge = "Round table" %}
        {% elsif type == "social" %}{% assign badge = "Social" %}
        {% elsif type == "meal" %}{% assign badge = "Meal" %}
        {% else %}{% assign badge = "Break" %}
        {% endif %}
        <div class="timeline-item" data-type="{{ type }}">
          <div class="session-card">
            <div class="session-head">
              <span class="session-badge badge-{{ type }}">{{ badge }}</span>
              <span class="session-time">{{ session.time }}</span>
            </div>
            <p class="session-title">{{ session.title }}</p>
            {% if session.speakers %}
            <p class="session-speakers">
              {% for sp in session.speakers %}{{ sp }}{% unless forloop.last %}, {% endunless %}{% endfor %}
            </p>
            {% endif %}
            {% if session.description %}
            <p class="session-desc">{{ session.description }}</p>
            {% endif %}
          </div>
        </div>
        {% endfor %}
      </div>
    </div>

    <!-- LEGEND -->
    <div class="program-legend" aria-label="Session type legend">
      <div class="legend-item"><span class="legend-dot" style="background:#2E5E8E;"></span> Plenary</div>
      <div class="legend-item"><span class="legend-dot" style="background:#3D7A5C;"></span> Session</div>
      <div class="legend-item"><span class="legend-dot" style="background:#7B4EA6;"></span> Workshop</div>
      <div class="legend-item"><span class="legend-dot" style="background:#C06B2A;"></span> Poster session</div>
      <div class="legend-item"><span class="legend-dot" style="background:#A04060;"></span> Round table</div>
      <div class="legend-item"><span class="legend-dot" style="background:#5A7A3A;"></span> Meal</div>
      <div class="legend-item"><span class="legend-dot" style="background:#8B6020;"></span> Social</div>
      <div class="legend-item"><span class="legend-dot" style="background:#8C8880;"></span> Break</div>
    </div>

  </div>
</section>

<script>
(function () {
  var tabs    = document.querySelectorAll('.tab-btn');
  var panels  = document.querySelectorAll('.day-panel');

  tabs.forEach(function (tab) {
    tab.addEventListener('click', function () {
      var target = document.getElementById(tab.getAttribute('aria-controls'));
      tabs.forEach(function (t) {
        t.classList.remove('is-active');
        t.setAttribute('aria-selected', 'false');
      });
      panels.forEach(function (p) { p.classList.remove('is-active'); });
      tab.classList.add('is-active');
      tab.setAttribute('aria-selected', 'true');
      if (target) target.classList.add('is-active');
    });
  });
})();
</script>
