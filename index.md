
---
layout: page
title: "Accueil"
description: "GAO YOBO'O - Le marché de Gao"
---

<div class="home-hero">
  <div class="diaporama">
    <img src="/assets/images/accueil/001.jpg" alt="Gao 1">
    <img src="/assets/images/accueil/002.jpg" alt="Gao 2">
    <img src="/assets/images/accueil/003.jpg" alt="Gao 3">
  </div>

  <div class="hero-cta">
    <h2>Bienvenue sur GAO YOBO'O</h2>
    <p>Le marché local de Gao en ligne — stands pour les commerçants, ressources pour la communauté.</p>
    <p class="buttons">
      <a class="btn" href="/boutiques">Voir les boutiques</a>
      <a class="btn" href="/location">Louer un stand</a>
      <a class="btn" href="/enregistrement">S'enregistrer</a>
    </p>
  </div>
</div>

## Aperçu des boutiques
<p>Voici quelques stands et boutiques — cliquez pour en savoir plus.</p>

<div class="vendors-preview">
  {% for v in site.vendors limit:6 %}
    <div class="card">
      <a href="{{ v.url | relative_url }}">
        {% if v.images and v.images[0] %}
          <img src="{{ v.images[0] | relative_url }}" alt="{{ v.title }}">
        {% else %}
          <img src="/assets/images/placeholders/stand-vide.jpg" alt="placeholder">
        {% endif %}
        <h3>{{ v.title }}</h3>
        {% if v.status == "inactive" %}
          <p class="muted">Stand disponible</p>
        {% else %}
          <p class="muted">{{ v.categories | join: ", " }}</p>
        {% endif %}
      </a>
    </div>
  {% endfor %}
</div>

##############################

boutiques.md

---
layout: page
title: "Boutiques"
---

# Toutes les boutiques et stands

<p>Liste de toutes les boutiques et stands (actifs et disponibles).</p>

<div class="vendors-list">
  {% for v in site.vendors %}
    <div class="vendor-row">
      <a href="{{ v.url | relative_url }}">
        <div class="thumb">
          {% if v.images and v.images[0] %}
            <img src="{{ v.images[0] | relative_url }}" alt="{{ v.title }}">
          {% else %}
            <img src="/assets/images/placeholders/stand-vide.jpg" alt="Stand vide">
          {% endif %}
        </div>
        <div class="info">
          <h3>{{ v.title }}</h3>
          {% if v.status == "inactive" %}
            <p class="status inactive">Disponible à la location</p>
          {% else %}
            <p>{{ v.excerpt | strip_html | truncate: 140 }}</p>
          {% endif %}
        </div>
      </a>
    </div>
  {% endfor %}
</div>