---
title: Publications
permalink: /publications/
layout: page
---

{% comment %}
  Group all publications by the 4-digit year extracted from date.
{% endcomment %}
{% assign pubs_by_year = site.publications 
    | group_by_exp: "item", "item.date | date: '%Y'" 
    | sort: "name" %}

{% for year_group in pubs_by_year reversed %}
  
**{{ year_group.name }}**

<ol class="pub-list">
  {% for pub in year_group.items %}
    <li>
      {% if pub.paperurl %}
        [{{ pub.title }}]({{ pub.paperurl }})
      {% else %}
        {{ pub.title }}
      {% endif %}, 
      *{{ pub.venue }}*, 
      {{ pub.date | date: "%Y" }}; 
      {{ pub.authors 
          | replace: "Debshikha Banerjee", "**Debshikha Banerjee**" 
      }}
    </li>
  {% endfor %}
</ol>

{% endfor %}
