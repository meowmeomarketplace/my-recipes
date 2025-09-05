---
layout: default
title: "Categories"
---

# Categories

<ul>
{% assign categories = site.recipes | map: "category" | uniq %}
{% for cat in categories %}
  <li>{{ cat }}
    <ul>
      {% for recipe in site.recipes %}
        {% if recipe.category == cat %}
          <li><a href="{{ recipe.url }}">{{ recipe.title }}</a></li>
        {% endif %}
      {% endfor %}
    </ul>
  </li>
{% endfor %}
</ul>

