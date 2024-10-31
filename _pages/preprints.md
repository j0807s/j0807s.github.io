---
layout: page
permalink: /preprints/
title: Preprints
description: 
years: [2024]
nav: true
nav_order: 4
---
<!-- _pages/preprints.md -->
<div class="publications">
  {% bibliography -f papers -q @*[selected=false]* %}
</div>

<!-- {%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{ y }}]*[selected=false] %}
{% endfor %} -->

