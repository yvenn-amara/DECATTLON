---
layout: default
title: Accueil
---

<!-- HERO -->
<section class="hero" style="margin-top: 64px;">
  <div class="container">
    <p class="hero-kicker">Workshop · 3–4 novembre 2026 · EDF Lab, Palaiseau</p>
    <h1 class="hero-title">Transfer Learning<br>et Modèles de Fondation</h1>
    <div class="hero-meta">
      <div class="hero-meta-item">
        <!-- Calendar icon -->
        <svg class="meta-icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.75" aria-hidden="true"><rect x="3" y="4" width="18" height="18" rx="2"/><line x1="3" y1="9" x2="21" y2="9"/><line x1="8" y1="2" x2="8" y2="6"/><line x1="16" y1="2" x2="16" y2="6"/></svg>
        3 et 4 novembre 2026
      </div>
      <div class="hero-meta-item">
        <!-- Location pin -->
        <svg class="meta-icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.75" aria-hidden="true"><path d="M12 21C12 21 5 13.5 5 9a7 7 0 0 1 14 0c0 4.5-7 12-7 12z"/><circle cx="12" cy="9" r="2.5"/></svg>
        EDF Lab, Palaiseau
      </div>
    </div>
    <div class="hero-actions">
      <a href="{{ '/program/' | relative_url }}" class="btn btn-primary">Voir le programme</a>
      <a href="{{ '/call-for-posters/' | relative_url }}" class="btn btn-outline">Soumettre un poster</a>
    </div>
  </div>
</section>

<!-- INTRO -->
<section class="section fade-in">
  <div class="container">
    <div class="intro-grid">
      <div class="intro-text">
        <h2>Contexte et objectifs</h2>
        <p class="lead">[PARAGRAPHE 1 — Contexte scientifique. Présentez en 3 à 5 phrases l'essor des modèles de fondation (LLM, vision transformers, modèles multimodaux) et leur impact sur la communauté du machine learning appliqué.]</p>
        <p>[PARAGRAPHE 2 — Enjeux spécifiques du transfer learning. Évoquez les défis d'adaptation de domaine, de fine-tuning efficace, de généralisation hors distribution, et les questions d'évaluation qui se posent aujourd'hui dans la recherche et l'industrie.]</p>
        <p>[PARAGRAPHE 3 — Objectifs du workshop. Décrivez ce que le workshop vise à accomplir : favoriser les échanges entre académiques et industriels, présenter des travaux récents, identifier des axes de collaboration, etc.]</p>
        <p>[PARAGRAPHE 4 — Public cible. Chercheurs en apprentissage automatique, ingénieurs data science, doctorants, post-doctorants travaillant sur les modèles de fondation ou leurs applications dans des domaines tels que la vision, le NLP, la série temporelle, etc.]</p>
      </div>
      <aside class="intro-aside">
        <h3>Thématiques abordées</h3>
        <ul class="aside-list">
          <li>Architectures de modèles de fondation (transformers, SSM, hybrides)</li>
          <li>Stratégies de fine-tuning : LoRA, adapters, prompt tuning</li>
          <li>Adaptation de domaine et transfert multi-tâches</li>
          <li>Évaluation robuste et benchmarks</li>
          <li>Applications industrielles et cas d'usage sectoriels</li>
          <li>Efficience computationnelle et déploiement</li>
          <li>[THÉMATIQUE 7 — à personnaliser]</li>
        </ul>
      </aside>
    </div>
  </div>
</section>

<!-- INTERVENANTS -->
<section class="section section--alt fade-in">
  <div class="container">
    <h2 class="mb-4">Intervenants</h2>
    <div class="speakers-grid">
      {% for speaker in site.data.speakers %}
      <div class="speaker-card">
        <div class="speaker-avatar">
          {% if speaker.photo != "" %}
          <img src="{{ speaker.photo | relative_url }}" alt="Photo de {{ speaker.name }}" />
          {% else %}
          <span class="avatar-initials">
            {{ speaker.name | split: ' ' | map: 'first' | join: '' | upcase | truncate: 2, '' }}
          </span>
          {% endif %}
        </div>
        <p class="speaker-name">{{ speaker.name }}</p>
        <p class="speaker-affil">{{ speaker.title }}{% if speaker.title != "" and speaker.affiliation != "" %}<br>{% endif %}{{ speaker.affiliation }}</p>
      </div>
      {% endfor %}
    </div>
  </div>
</section>

<!-- CTA -->
<section class="section section--accent fade-in">
  <div class="container text-center">
    <h2>Rejoignez-nous</h2>
    <p class="lead mt-2" style="max-width: 560px; margin-left: auto; margin-right: auto;">
      La session posters est ouverte aux contributions de la communauté. Soumettez votre résumé avant la date limite.
    </p>
    <div class="hero-actions mt-4" style="justify-content: center;">
      <a href="{{ '/call-for-posters/' | relative_url }}" class="btn btn-primary">Appel à contributions →</a>
      <a href="{{ '/venue/' | relative_url }}" class="btn btn-outline">Infos pratiques</a>
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
