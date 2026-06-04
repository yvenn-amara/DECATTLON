---
layout: default
title: Programme
description: Programme détaillé des deux journées du workshop.
---

<div class="page-hero">
  <div class="container">
    <p class="page-kicker">Workshop — 3–4 novembre 2026</p>
    <h1>Programme</h1>
    <p class="lead">Deux journées de sessions plénières, ateliers, tables rondes et présentations posters autour du transfer learning et des modèles de fondation.</p>
  </div>
</div>

<section class="section">
  <div class="container">

    <!-- TABS -->
    <div class="program-tabs" role="tablist" aria-label="Jours du workshop">
      <button class="tab-btn is-active" role="tab" aria-selected="true"  aria-controls="day1" id="tab-day1">Jour 1 — Mardi 3 nov.</button>
      <button class="tab-btn"           role="tab" aria-selected="false" aria-controls="day2" id="tab-day2">Jour 2 — Mercredi 4 nov.</button>
    </div>

    <!-- DAY 1 -->
    <div id="day1" class="day-panel is-active" role="tabpanel" aria-labelledby="tab-day1">
      <p class="day-label">{{ site.data.program.day1.label }}</p>
      <div class="timeline">
        {% assign badge_labels = "plenary|Plénière,session|Session,workshop|Atelier,poster|Posters,panel|Table ronde,social|Social,meal|Repas,break|Pause" | split: ',' %}
        {% for session in site.data.program.day1.sessions %}
        {% assign type = session.type %}
        {% if type == "plenary" %}{% assign badge = "Plénière" %}
        {% elsif type == "session" %}{% assign badge = "Session" %}
        {% elsif type == "workshop" %}{% assign badge = "Atelier" %}
        {% elsif type == "poster" %}{% assign badge = "Posters" %}
        {% elsif type == "panel" %}{% assign badge = "Table ronde" %}
        {% elsif type == "social" %}{% assign badge = "Social" %}
        {% elsif type == "meal" %}{% assign badge = "Repas" %}
        {% else %}{% assign badge = "Pause" %}
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
        {% if type == "plenary" %}{% assign badge = "Plénière" %}
        {% elsif type == "session" %}{% assign badge = "Session" %}
        {% elsif type == "workshop" %}{% assign badge = "Atelier" %}
        {% elsif type == "poster" %}{% assign badge = "Posters" %}
        {% elsif type == "panel" %}{% assign badge = "Table ronde" %}
        {% elsif type == "social" %}{% assign badge = "Social" %}
        {% elsif type == "meal" %}{% assign badge = "Repas" %}
        {% else %}{% assign badge = "Pause" %}
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
    <div class="program-legend" aria-label="Légende des types de session">
      <div class="legend-item"><span class="legend-dot" style="background:#2E5E8E;"></span> Plénière</div>
      <div class="legend-item"><span class="legend-dot" style="background:#3D7A5C;"></span> Session</div>
      <div class="legend-item"><span class="legend-dot" style="background:#7B4EA6;"></span> Atelier</div>
      <div class="legend-item"><span class="legend-dot" style="background:#C06B2A;"></span> Session posters</div>
      <div class="legend-item"><span class="legend-dot" style="background:#A04060;"></span> Table ronde</div>
      <div class="legend-item"><span class="legend-dot" style="background:#5A7A3A;"></span> Repas</div>
      <div class="legend-item"><span class="legend-dot" style="background:#8B6020;"></span> Social</div>
      <div class="legend-item"><span class="legend-dot" style="background:#8C8880;"></span> Pause</div>
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
