---
layout: default
title: Home
---

<!-- HERO -->
<section class="hero" style="margin-top: 64px;">
  <div class="container">
    <p class="hero-kicker">Workshop · November 3–4, 2026 · EDF Lab, Palaiseau</p>
    <h1 class="hero-title">Transfer Learning<br>and TSFM</h1>
    <div class="hero-meta">
      <div class="hero-meta-item">
        <!-- Calendar icon -->
        <svg class="meta-icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.75" aria-hidden="true"><rect x="3" y="4" width="18" height="18" rx="2"/><line x1="3" y1="9" x2="21" y2="9"/><line x1="8" y1="2" x2="8" y2="6"/><line x1="16" y1="2" x2="16" y2="6"/></svg>
        November 3 and 4, 2026
      </div>
      <div class="hero-meta-item">
        <!-- Location pin -->
        <svg class="meta-icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.75" aria-hidden="true"><path d="M12 21C12 21 5 13.5 5 9a7 7 0 0 1 14 0c0 4.5-7 12-7 12z"/><circle cx="12" cy="9" r="2.5"/></svg>
        EDF Lab, Palaiseau
      </div>
    </div>
    <div class="hero-actions">
      <a href="{{ '/program/' | relative_url }}" class="btn btn-primary">View the program</a>
      <a href="https://framaforms.org/transfer-learning-and-time-series-fm-1781970359" class="btn btn-outline">Register and/or submit a poster</a>
    </div>
  </div>
</section>

<!-- INTRO -->
<section class="section fade-in">
  <div class="container">
    <div class="intro-grid">
      <div class="intro-text">
        <h2>Context and Objectives</h2>
        <p class="lead">This event, co-organized by the <a href="https://anr.fr/Projet-ANR-24-CE40-3341" target="_blank" rel="noopener noreferrer">ANR DECATTLON project</a> and <a href="https://www.edf.fr/groupe-edf/innover/rd-un-savoir-faire-mondial" target="_blank" rel="noopener noreferrer">EDF R&amp;D</a>, and sponsored by the <a href="https://enbis.org/activities/ln/frenbis/" target="_blank" rel="noopener noreferrer">French network of ENBIS (frENBIS)</a>, is part of the initiatives to promote statistics and machine learning methods within companies and industry.
Transfer learning marked a turning point by enabling the reuse of knowledge acquired on one task to solve another, thereby optimizing resources and data. With the emergence of foundation models – general and powerful architectures like Transformers – this approach has undergone a new revolution. These models, pre-trained on massive volumes of data, provide universal bases that are easily adaptable to specific applications through advanced transfer learning techniques. They thus redefine the practices of personalization and efficiency in artificial intelligence.</p>
      </div>
      <aside class="intro-aside">
        <h3>Topics Covered</h3>
        <ul class="aside-list">
          <li>Foundation model architectures (transformers, SSM, hybrid)</li>
          <li>Fine-tuning strategies: LoRA, adapters, prompt tuning</li>
          <li>Domain adaptation and multi-task transfer</li>
          <li>Robust evaluation and benchmarks</li>
          <li>Industrial applications and industry use cases</li>
          <li>Computational efficiency and deployment</li>
        </ul>
      </aside>
    </div>
  </div>
</section>

<!-- SPEAKERS --> 
<section class="section section--alt fade-in">
  <div class="container">
    <h2 class="mb-4">Speakers</h2>
    <div class="speakers-grid">
      {% for speaker in site.data.speakers %}
      <div class="speaker-card">
        <div class="speaker-avatar">
          {% if speaker.photo != "" %}
          <img src="{{ speaker.photo | relative_url }}" alt="Photo of {{ speaker.name }}" />
          {% else %}
          <span class="avatar-initials">
            {{ speaker.name | split: " " | map: "first" | join: "" }}
          </span>
          {% endif %}
        </div>

        {% if speaker.website and speaker.website != "" %}
        <a href="{{ speaker.website }}" class="speaker-name" target="_blank" rel="noopener">{{ speaker.name }}</a>
        {% else %}
        <p class="speaker-name">{{ speaker.name }}</p>
        {% endif %}

        <p class="speaker-affil">
          {{ speaker.title }}
          {% if speaker.title != "" and speaker.affiliation != "" %}<br>{% endif %}
          {{ speaker.affiliation }}
        </p>

        {% if speaker.bio and speaker.bio != "" %}
        <p class="speaker-bio">{{ speaker.bio }}</p>
        {% endif %}
      </div>
      {% endfor %}
    </div>
  </div>
</section>

<!-- CTA -->
<section class="section section--accent fade-in">
  <div class="container text-center">
    <h2>Join us</h2>
    <p class="lead mt-2" style="max-width: 560px; margin-left: auto; margin-right: auto;">
      The poster session is open for contributions. Submit your abstract before the deadline.
    </p>
    <div class="hero-actions mt-4" style="justify-content: center;">
      <a href="{{ '/call-for-posters/' | relative_url }}" class="btn btn-primary">Call for contributions →</a>
      <a href="{{ '/venue/' | relative_url }}" class="btn btn-outline">Practical Info</a>
    </div>
  </div>
</section>

<script>
(function () {
  var elements = document.querySelectorAll('.fade-in');
  if (!elements.length) return;
  var observer = new IntersectionObserver(function (entries) {
    entries.forEach(function (entry) {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.1 });
  elements.forEach(function (el) { observer.observe(el); });
})();
</script>
