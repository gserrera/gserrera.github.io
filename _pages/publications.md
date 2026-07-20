---
layout: page
permalink: /publications/
title: Publications
description: Publications and presented posters in reversed chronological order. PDFs and full citations are provided.
nav: true
nav_order: 2
social: true # includes social icons at the bottom of the page
---



<!-- _pages/publications.md -->

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

{% bibliography --query @*[keywords~=publication] %}

</div>
