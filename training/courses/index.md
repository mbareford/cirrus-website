---
layout: section
title: Cirrus Training
summary: Training opportunities for Cirrus users
---


## Upcoming Cirrus Training



<br>

   








<div class="table-responsive">
  <table >
    <thead>
      <tr>
        <th>Course</th>
        <th>Venue</th>
        <th>Dates</th>
        <th>Register Link</th>
      </tr>
    </thead>
    <tbody>
      {% assign filtered_courses = site.courses | where_exp: "course", "course.end_date >= site.time" %}
			{% assign nothidden_courses = filtered_courses | where_exp: "course", "course.registration_status != 'hidden' " %}
      {% for course in nothidden_courses %}
      <tr>
      <td>
        <a href="{{ course.url }}">{{ course.title }}</a>
      </td>
      <td>
        {% if course.location != "Online" %}
          <a href="{{ site.baseurl }}{{ course.location_url }}">{{ course.location }}</a>
        {% else %}
          {{ course.location }}
        {% endif %}
      </td>
      <td>
        {{ course.human_dates }}
      </td>
      <td>
        {% if course.course_type == "vt" %}
          <a href="{{ course.url }}">More details and join link</a>
        {% else %}
          {% if course.registration_url %}
            {% if course.registration_status == "open" %}
              {% if course.prace_course %}
            <a href="{{ course.registration_url }}"><img src="img/prace_25.jpg" alt="PRACE"/> Register</a>
              {% else %}
            <a href="{{ course.registration_url }}">Register</a>
              {% endif %}
            {% elsif course.registration_status == "full" %}
              {% if course.prace_course %}
            <a href="{{ course.registration_url }}"><img src="img/prace_25.jpg" alt="PRACE"/> Join waiting list</a>
              {% else %}
            <a href="{{ course.registration_url }}">Join waiting list</a>
              {% endif %}
            {% elsif course.registration_status == "closed" %}
              {% if course.prace_course %}
            <a href="{{ course.registration_url }}"><img src="img/prace_25.jpg" alt="PRACE"/> Registration closed</a>
              {% else %}
            Registration closed
              {% endif %}
            {% else %}
            &nbsp;
            {% endif %}
          {% endif %}
        {% endif %}
      </td>
     </tr>
      {% endfor %}
    </tbody>
  </table>

</div>