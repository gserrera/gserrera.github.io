---
layout: page
permalink: /teaching/
title: teaching
description: Courses in which I have taught.
nav: true
nav_order: 6
---

<!-- _pages/teaching.md -->

<!-- Teaching Data Feature -->

{% include teaching_search.liquid %}

<div class="teaching">

{% for year in site.data.teaching | sort: "year" | reverse %}
### {{ year.year }}

{% for course in year.courses %}
- **{{ course.title }}** ({{ course.level }}, {{ course.semester }})  
  {% if course.description %}{{ course.description }}{% endif %}
{% endfor %}

{% endfor %}

---

## Mentorship

{% for mentorship in site.data.mentorships %}
- **{{ mentorship.student_level }}**  
  - {{ mentorship.name }} ({{ mentorship.period }}) – {{ mentorship.project }}
{% endfor %}

</div>
