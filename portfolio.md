---
title: "Aerospace Engineering Portfolio"
permalink: /portfolio/
# Abbiamo rimosso layout: archive per bypassare il conflitto.
---

## 🚀 Technical Projects and Simulations

{% assign projects = site.projects | sort: 'date' | reverse %}

{% for project in projects %}
  <div class="archive__item">
    <h2 class="archive__item-title">
      <a href="{{ project.url | relative_url }}">{{ project.title }}</a>
    </h2>
    <p class="archive__item-excerpt">{{ project.excerpt }}</p>
    <p><small>Ultimo aggiornamento: {{ project.last_modified_at | date: "%B %d, %Y" }}</small></p>
  </div>
  <hr>
{% endfor %}
