---
layout: page
permalink: /preprints/
title: Preprints
description: 
years: [2023,2022, 2021]
nav: true
nav_order: 4
---
<!-- _pages/preprints.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[selected=false]* %}
{% endfor %}

</div>
