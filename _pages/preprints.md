---
layout: page
permalink: /preprints/
title: Preprints
description: 
years: [2023,2022, 2021]
nav: true
nav_order: 1
---
<!-- _pages/publications.md -->
<div class="preprints">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>