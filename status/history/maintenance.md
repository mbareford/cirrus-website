---
layout: section
title: Cirrus Service Status
summary: Log of Cirrus service Maintenance
---

&nbsp;

- [Q2 2022](#maintenance-sessions-quarter-2-2022-1st-april---30th-june-2022)
- [Q1 2022](#maintenance-sessions-quarter-1-2022-1st-january---31st-march-2022)
- [Q4 2021](#maintenance-sessions-quarter-4-2021-1st-october---31st-december-2021)


{% assign maintenance_2022_q2 = site.maintenance | where_exp: "maintenance", "maintenance.quarter == '2022_q2'" %}
{% for maintenance in maintenance_2022_q2 reversed %}

    {% if forloop.first == true %}

## Maintenance Sessions: Quarter 2 2022 (1st April - 30th June 2022)

  <table >
    <thead>
      <tr>
        <th>Status</th>
        <th>Type</th>
        <th>Start</th>
        <th>End</th>
        <th>System</th>
        <th>User Impact</th>
        <th>Reason</th>
      </tr>
    </thead>

    <tbody>
    {% endif %}
      <tr>
      <td>
        {{ maintenance.status }}
      </td>
      <td>
        {{ maintenance.type }}
      </td>
      <td>
        {{ maintenance.start_date }}
      </td>
      <td>
        {{ maintenance.end_date }}
      </td>
      <td>
        {{ maintenance.system }}
      </td>
      <td>
        {{ maintenance.impact }}
      </td>
      <td>
        {{ maintenance.reason }}
      </td>
      </tr>
    {% if forloop.last == true %}
    </tbody>
  </table>
    {% endif %}
{% endfor %}




{% assign maintenance_2022_q1 = site.maintenance | where_exp: "maintenance", "maintenance.quarter == '2022_q1'" %}
{% for maintenance in maintenance_2022_q1 reversed %}

    {% if forloop.first == true %}

## Maintenance Sessions: Quarter 1 2022 (1st January - 31st March 2022)

  <table >
    <thead>
      <tr>
        <th>Status</th>
        <th>Type</th>
        <th>Start</th>
        <th>End</th>
        <th>System</th>
        <th>User Impact</th>
        <th>Reason</th>
      </tr>
    </thead>

    <tbody>
    {% endif %}
      <tr>
      <td>
        {{ maintenance.status }}
      </td>
      <td>
        {{ maintenance.type }}
      </td>
      <td>
        {{ maintenance.start_date }}
      </td>
      <td>
        {{ maintenance.end_date }}
      </td>
      <td>
        {{ maintenance.system }}
      </td>
      <td>
        {{ maintenance.impact }}
      </td>
      <td>
        {{ maintenance.reason }}
      </td>
      </tr>
    {% if forloop.last == true %}
    </tbody>
  </table>
    {% endif %}
{% endfor %}





{% assign maintenance_2021_q4 = site.maintenance | where_exp: "maintenance", "maintenance.quarter == '2021_q4'" %}
{% for maintenance in maintenance_2021_q4 reversed %}

    {% if forloop.first == true %}

## Maintenance Sessions: Quarter 4 2021 (1st October - 31st December 2021)

  <table >
    <thead>
      <tr>
        <th>Status</th>
        <th>Type</th>
        <th>Start</th>
        <th>End</th>
        <th>System</th>
        <th>User Impact</th>
        <th>Reason</th>
      </tr>
    </thead>

    <tbody>
    {% endif %}
      <tr>
      <td>
        {{ maintenance.status }}
      </td>
      <td>
        {{ maintenance.type }}
      </td>
      <td>
        {{ maintenance.start_date }}
      </td>
      <td>
        {{ maintenance.end_date }}
      </td>
      <td>
        {{ maintenance.system }}
      </td>
      <td>
        {{ maintenance.impact }}
      </td>
      <td>
        {{ maintenance.reason }}
      </td>
      </tr>
    {% if forloop.last == true %}
    </tbody>
  </table>
    {% endif %}
{% endfor %}







