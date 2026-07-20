---
layout: page
title: Events
permalink: /events/
description: Upcoming and past conferences and events. Posters and abstracts are provided in PDF.
nav: true
nav_order: 3
social: true # includes social icons at the bottom of the page
---

# Upcoming events

{% include events.liquid %}

# Past Contributions

{% include bib_search.liquid %}

<div class="publications">

{% bibliography --query @*[keywords~=conference] %}

</div>
