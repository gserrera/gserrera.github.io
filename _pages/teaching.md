---
layout: page
permalink: /teaching/
title: Teaching
description: Courses and mentorships in reverse chronological order.
nav: true
nav_order: 6
---

<!-- _pages/teaching.md -->

<div class="teaching">

{% assign sorted_teaching = site.data.teaching | sort: "year" | reverse %}

{% for year_entry in sorted_teaching %}
  <div class="teaching-year">
    <div class="entry-header">
      <span class="entry-title">{{ year_entry.year }}</span>
    </div>
    <ul class="teaching-courses">
      {% for course in year_entry.courses %}
      <li class="course-item">
        <strong>{{ course.title }}</strong><br>
        <em>{{ course.level }}</em><br>
        <small>{{ course.semester }}</small><br>
        {% if course.description %}
          {{ course.description }}
        {% endif %}
      </li>
      {% endfor %}
    </ul>
    {% unless forloop.last %}
    <hr>
    {% endunless %}
  </div>
{% endfor %}

<hr>

<h2 class="section-title">Mentorships</h2>
<div class="mentorships">
  {% if site.data.mentorships %}
    {% for mentor in site.data.mentorships %}
    <div class="mentorship-entry">
      <strong>{{ mentor.name }}</strong><br>
      <em>{{ mentor.type }}</em> — {{ mentor.year }}<br>
      {% if mentor.notes %}
        <span class="mentorship-notes">{{ mentor.notes }}</span>
      {% endif %}
    </div>
    {% endfor %}
  {% else %}
    <p>No mentorship data available.</p>
  {% endif %}
</div>

</div>

<style>
.section-title,
.teaching h2 {
  font-size: 1.1em; /* smaller section titles */
  font-weight: 600;
  color: var(--text-color, #333);
  margin-top: 1.8em;
  margin-bottom: 0.8em;
}

.teaching-year {
  margin-bottom: 2em;
}

.entry-header {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  margin-bottom: 0.5em;
}

.entry-title {
  font-size: 1em;
  font-weight: 600;
  color: var(--text-color, #333);
}

.teaching-courses {
  list-style-type: none;
  padding-left: 0;
  margin-top: 0.3em;
}

.course-item {
  margin-bottom: 0.8em;
  line-height: 1.4;
}

.mentorships {
  font-size: 1em;
  margin-top: 1.5em;
}

.mentorship-entry {
  margin-bottom: 1em;
  line-height: 1.4;
}

.mentorship-notes {
  color: #555;
  font-size: 0.95em;
}

hr {
  border: 0;
  border-top: 1px solid #ddd;
  margin: 1.5em 0;
}
</style>
