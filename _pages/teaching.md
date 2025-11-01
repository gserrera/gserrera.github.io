---
layout: page
permalink: /teaching/
title: Teaching
description: Courses and mentorships in reverse chronological order.
nav: true
nav_order: 6
---

# Teaching Activities

This page lists the courses I have taught, organized in **reverse chronological order** by academic year.  
A final section lists my mentorship activities.

---

{% assign sorted_teaching = site.data.teaching | sort: "year" | reverse %}

{% for year_entry in sorted_teaching %}
## {{ year_entry.year }}

{% for course in year_entry.courses %}
- **{{ course.title }}**  
  _{{ course.level }} — {{ course.semester }}_  
  {{ course.description }}
{% endfor %}

{% unless forloop.last %}
---
{% endunless %}

{% endfor %}

---

## Mentorships

{% if site.data.mentorships %}
{% for mentor in site.data.mentorships %}
- **{{ mentor.name }}**  
  _{{ mentor.type }}, {{ mentor.year }}_  
  {% if mentor.notes %}{{ mentor.notes }}{% endif %}
{% endfor %}
{% else %}
_No mentorship data available._
{% endif %}

