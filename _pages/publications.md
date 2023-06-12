---
layout: page
permalink: /publications/
title: publications
description: 
years: [2023, 2022, 2021, 2020 ]
years_conf: [2014, 2016, 2017, 2022]
nav: true
nav_order: 1
---

## Journals
<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f {{ site.scholar.bibliography }} -q @*[year={{y}}]* %}
{% endfor %}

</div>

## Conferences

<div class="publications">

{%- for y in page.years_conf %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f {{ site.scholar.bibliography_conf }} -q @*[year={{y}}]* %}
{% endfor %}

</div>