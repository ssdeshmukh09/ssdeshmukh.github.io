---
layout: page
permalink: /publications/
title: publications
description: An up-to-date list is available on <a href="https://scholar.google.co.in/citations?user=MasiEogAAAAJ&hl=en" target="_blank">Google Scholar</a>
years: [2021, 2020, 2019, 2018]
nav: true
---

<div class="publications">

{% for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
