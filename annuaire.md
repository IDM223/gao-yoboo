
---
layout: page
title: "Annuaire"
---

# Annuaire du marché

<p>Retrouvez les boutiques par catégorie.</p>

{% for cat in site.data.categories %}
  <section class="category">
    <h2>{{ cat | capitalize }}</h2>
    <ul>
      {% assign matches = site.vendors | where_exp: "item", "item.categories contains '" | append: cat | append: "'" %}
      {% for m in matches %}
        <li><a href="{{ m.url | relative_url }}">{{ m.title }}</a> {% if m.status == "inactive" %}<span class="muted"> (Disponible)</span>{% endif %}</li>
      {% endfor %}
    </ul>
  </section>
{% endfor %}