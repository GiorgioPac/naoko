---
title: "Aerospace Engineering Portfolio"
permalink: /portfolio/
# Abbiamo rimosso layout: archive per bypassare il conflitto.
---

Welcome to my technical portfolio. This section showcases the most significant aerodynamics and fluid dynamics projects conducted during my Master's degree in Aeronautical Engineering.

## 🚀 University and Personal Projects

{% assign projects = site.projects | sort: 'date' | reverse %}

{% for project in projects %}
  <div class="archive__item">
    <h2 class="archive__item-title">
      <a href="{{ project.url | relative_url }}">{{ project.title }}</a>
    </h2>
    <p class="archive__item-excerpt">{{ project.excerpt }}</p>
  </div>
  <hr>
{% endfor %}
