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
    <div class="teaching-entry">
      <div class="entry-header">
        <span class="entry-title"><strong>{{ year_entry.year }}</strong></span>
      </div>
      <ul class="teaching-courses">
        {% for course in year_entry.courses %}
        <li class="course-item">
          <span class="course-info">
            <strong>{{ course.title }}</strong><br>
            <em>{{ course.level }}</em><br>
            <small>{{ course.semester }}</small><br>
            {% if course.description %}
              {{ course.description }}
            {% endif %}
          </span>
        </li>
        {% endfor %}
      </ul>
    </div>
    {% unless forloop.last %}
    <hr>
    {% endunless %}
  </div>
{% endfor %}

<hr>

<h2>Mentorships</h2>
<div class="mentorships">
  {% if site.data.mentorships %}
    {% for mentor in site.data.mentorships %}
    <div class="mentorship-entry">
      <div class="mentorship-info">
        <strong>{{ mentor.name }}</strong><br>
        <em>{{ mentor.type }}</em> — {{ mentor.year }}<br>
        {% if mentor.notes %}
          <span class="mentorship-notes">{{ mentor.notes }}</span>
        {% endif %}
      </div>
    </div>
    {% endfor %}
  {% else %}
    <p>No mentorship data available.</p>
  {% endif %}
</div>

</div>

<style>
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
  font-size: 1.2em;
  font-weight: 600;
  color: var(--text-color, #333);
}
.teaching-courses {
  list-style-type: none;
  padding-left: 0;
}
.course-item {
  margin-bottom: 0.8em;
}
.course-info {
  display: block;
  line-height: 1.4;
}
.mentorship-entry {
  margin-bottom: 1em;
}
.mentorship-info {
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
