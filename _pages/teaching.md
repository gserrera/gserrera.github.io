---
layout: page
permalink: /teaching/
title: Teaching
description: Courses and mentorships in reverse chronological order.
nav: true
nav_order: 6
---

{% comment %}
This page displays your teaching duties from _data/teaching.yml
in reverse chronological order. A final section shows mentorships.
{% endcomment %}

<div class="teaching">

{% assign sorted_teaching = site.data.teaching | sort: "year" | reverse %}

{% for year_entry in sorted_teaching %}
  <h2>{{ year_entry.year }}</h2>
  <ul>
    {% for course in year_entry.courses %}
      <li>
        <strong>{{ course.title }}</strong> ({{ course.level }}) — {{ course.semester }}<br>
        {{ course.description }}
      </li>
    {% endfor %}
  </ul>
{% endfor %}

<h2>Mentorships</h2>
<ul>
  {% for mentor in site.data.mentorships %}
    <li>
      <strong>{{ mentor.name }}</strong> — {{ mentor.type }} ({{ mentor.year }})
      {% if mentor.notes %}: {{ mentor.notes }}{% endif %}
    </li>
  {% endfor %}
</ul>

</div>
