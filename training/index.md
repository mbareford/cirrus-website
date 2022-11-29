---
layout: section
title: Cirrus Training
summary: Training opportunities for Cirrus users
---


## Upcoming Cirrus Training

### [UK National Open Hackathon 2023](https://www.openhackathons.org/s/siteevent/a0C5e000005V6EDEA0/se000151)

[The UK National Open Hackathon](https://www.openhackathons.org/s/siteevent/a0C5e000005V6EDEA0/se000151) partnered with EPSRC, NVIDIA, and OpenACC.org will be designed for teams to work in productive sprint sessions with expert mentors for the duration of the [event](230306-uk-national-open-hackathon).





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



## Upcoming Training relevant for Cirrus users

### Training offered by [ARCHER2](https://www.archer2.ac.uk) service but relevant for Cirrus

All courses are free for UK academics and Cirrus users are warmly invited to attend.

Some courses use ARCHER2, other will use laptops only.  Temporary ARCHER2 machine access will be provided for the duration of the course wherever needed.

<br>

| Course | Venue |	Dates |	Register Link |
| --- | ---      | ---    | --- |
|[Advanced OpenMP](https://www.archer2.ac.uk/training/courses/221129-advanced-openmp/) |	Online |	29 - 30 November 2022 09:00 - 17:00 GMT | 	[ Register](https://events.prace-ri.eu/event/1462/registrations/1078/) |
| [Reproducible computational environments using containers](https://www.archer2.ac.uk/training/courses/221207-containers/) | 	[Newcastle University](https://www.archer2.ac.uk/training/locations/newcastle) |	7 - 8 December 2022 10:30 - 16:30 GMT |	[Register](https://www.archer2.ac.uk/training/register/?course=221207-containers) |
| [Introduction to Modern Fortran](https://www.archer2.ac.uk/training/courses/221213-modern-fortran/) |	[Oxford e-Science Research Centre](https://www.archer2.ac.uk/training/locations/oxford) |	13 - 14 December 2022 09:30 - 16:30 GMT |	[ Register](https://events.prace-ri.eu/event/1467/registrations/1083/) |


<br>
See [all upcoming ARCHER2 training](https://www.archer2.ac.uk/training/#upcoming-training)

See [resources for past ARCHER2 training](https://www.archer2.ac.uk/training/materials/)


### Other Training relevant for Cirrus users

- None at present
