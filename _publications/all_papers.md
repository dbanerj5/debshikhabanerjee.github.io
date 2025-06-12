---
title: Publications
permalink: /publications/
layout: page
---

<ul class="publications-list">
  {% assign pubs = site.publications | sort: "date" | reverse %}
  {% for pub in pubs %}
    <li>
      {% if pub.paperurl %}
        <a href="{{ pub.paperurl }}">{{ pub.title }}</a>
      {% else %}
        {{ pub.title }}
      {% endif %}
      {% if pub.authors %} — {{ pub.authors }}{% endif %}
      {% if pub.venue %}, <em>{{ pub.venue }}</em>{% endif %}
      ({{ pub.date | date: "%Y" }})
    </li>
  {% endfor %}
</ul>
