---
layout: section
title: Cirrus Service Status
summary: Up to date status of the Cirrus service
---

&nbsp;

- [Current System Load](#current-system-load)
- [Known Issues](#known-issues)
- [Current Issues](#service-alerts)
- [Recent Issues](#recently-resolved-service-alerts)
- [Maintenance](#service-calendar-and-maintenance)
- [Module Updates](#module-updates)
- [Service Calendar and Maintenance](#service-calendar-and-maintenance)

## Current System Load

The plot below shows the status of the CPU nodes on the current Cirrus service for the past day
(note: the Cirrus GPU nodes are not included in this plot).

A description of each of the status types is provided below the plot.

### CPU

![Cirrus Node Status graph](https://safe.epcc.ed.ac.uk/Graphs/cirrus.png)
{: style="width=80%" align="center"
alt="Cirrus Node Status over time" 
title="Cirrus Node Status over time"}

- *alloc*: Nodes running user jobs
- *idle*: Nodes available for user jobs
- *resv*: Nodes in reservation and not available for standard user jobs
- *down*, *drain*, *maint*, *drng*, *comp*: Nodes unavailable for user jobs
- *mix*: Nodes in multiple states 

### GPU
![Cirrus GPU Node Status graph](https://safe.epcc.ed.ac.uk/Graphs/cirrus_gpu.png)
{: style="width=80%" align="center"
alt="Cirrus Node Status over time" 
title="Cirrus Node Status over time"}

- *alloc*: Nodes running user jobs
- *idle*: Nodes available for user jobs
- *resv*: Nodes in reservation and not available for standard user jobs
- *down*, *drain*, *maint*, *drng*, *comp*: Nodes unavailable for user jobs
- *mix*: Nodes in multiple states 



## Known Issues 

We are experiening a heavy load on the metadata server. Our systems team are investigating but we suspect this is due to user(s) performing many I/O operations. We apologise for the inconvenience this is causing users. 

## Service Alerts


{% assign current_alerts = site.alerts | where_exp: "alert", "alert.status == 'Ongoing'" %}
{% for alert in current_alerts reversed %}
    {% if forloop.first == true %}

  <table>
    <thead>
      <tr>
        <th>Status</th>
        <th>Type</th>
        <th>Start</th>
        <th>End</th>
        <th>Scope</th>
        <th>User Impact</th>
        <th>Reason</th>
      </tr>
    </thead>
    <tbody>
    {% endif %}
      <tr>
      <td>
        {{ alert.status }}
      </td>
      <td>
        {{ alert.type }}
      </td>
      <td>
        {{ alert.start_date | date: "%Y-%m-%d %H:%M" }}
      </td>
      <td>
        {{ alert.end_date | date: "%Y-%m-%d %H:%M" }}
      </td>
      <td>
        {{ alert.scope }}
      </td>
      <td>
        {{ alert.impact }}
      </td>
      <td>
        {{ alert.reason }}
      </td>
     </tr>
    {% if forloop.last == true %}
    </tbody>
  </table>

    {% endif %}
{% else %}
<p>No current service alerts</p>
{% endfor %}

 

## Recently Resolved Service Alerts

This table lists resolved service alerts from the past 30 days. 
[A full list of historical resolved service alerts is available](history/alerts).

{% assign resolved_alerts = site.alerts | where_exp: "alert", "alert.status == 'Resolved'" %}
{% assign date_now = "now" | date: "%s" %}
{% assign date_thresh = date_now | minus: 2592000 | date: "%s" %}
{% assign count = 0 %}
{% for alert in resolved_alerts reversed %}
    {% assign ed = alert.end_date | date: "%s" %}
    {% if ed > date_thresh %}
        {% if count == 0 %}

  <table >
    <thead>
      <tr>
        <th>Status</th>
        <th>Type</th>
        <th>Start</th>
        <th>End</th>
        <th>Scope</th>
        <th>User Impact</th>
        <th>Reason</th>
      </tr>
    </thead>
    <tbody>
        {% endif %}
      <tr>
      <td>
        {{ alert.status }}
      </td>
      <td>
        {{ alert.type }}
      </td>
      <td>
        {{ alert.start_date | date: "%Y-%m-%d %H:%M"  }}
      </td>
      <td>
        {{ alert.end_date | date: "%Y-%m-%d %H:%M"  }}
      </td>
      <td>
        {{ alert.scope }}
      </td>
      <td>
        {{ alert.impact }}
      </td>
      <td>
        {{ alert.reason }}
      </td>
      </tr>
        {% assign count = count | plus: 1 %}
    {% endif %}
{% endfor %}
{% if count > 0 %}
    </tbody>
  </table>
{% else %}
<p>No recent service alerts</p>
{% endif %}



## Service Calendar and Maintenance

## Maintenance Sessions:Quarter 4 2022 (1st October - 31st December 2022)

{% assign maintenance_2022_q2 = site.maintenance | where_exp: "maintenance", "maintenance.quarter >= '2022_q2'" %}
{% for maintenance in maintenance_2022_q2 reversed %}

    {% if forloop.first == true %}
### Quarter 4 2022 (1st October - 31st December 2022)


  <table>
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
{% else %}
<p>No scheduled maintenance</p>
{% endfor %}


## Maintenance Logs for previous periods

[Previous maintenance logs](history/maintenance)



## Module Updates 

Module Update following Cirrus Upgrade September 2022 
  
| Description | Reason | Advice |
| ---    | ---  | ---   | 
| Removed Molpro module and user doc section | No longer functional | No longer centrally supported on Cirrus |
| Forge to be updated	| v20.0.3 found to have security flaw | Pending. Newer version will be installed as a replacement. |
| Updated mpi4py | All the mpi4py modules are tied to a particular version of python, 3.8.12. More flexibility is required such that users can run python-based parallel code using different python versions. | The mpi4py modules have been replaced by a suite of python modules: python/3.8.13, python/3.8.13-gpu, python/3.9.12, and python/3.9.12-gpu. The gpu modules load a miniconda3 python environment containing mpi4py 3.1.3 linked with OpenMPI 4.1.x and CUDA 11.6; whereas the cpu modules (no -gpu suffix) load a python environment containing mpi4py 3.1.3 linked with HPE MPT 2.25. (The python/3.8.13-gpu module is linked with OpenMPI 4.1.2 and the python/3.9.12-gpu module is linked with OpenMPI 4.1.4.) |
| Updated horovod | Updated | Module version 0.24.2-gpu has been replaced by 0.25.0-gpu. |
| Updated pytorch | Updated | Module version 1.11.0-gpu has been replaced by 1.12.0-gpu. |
| Updated tensorflow | Updated | Module version 2.8.0-gpu has been replaced by 2.9.1-gpu. |
| Updated scalasca	| Version 2.5 no longer functional. | Please use 2.6-gcc8-mpt225 or 2.6-intel19-mpt225 instead. |
| Removed spack/2020 module | Not used. | Not required. Please contact the service desk if Spack installation is needed. |
| Updated tmux | Version 3.1b no longer functional. | Version 3.3a provided as replacement. |


## At Risk Maintenance Sessions

There is an 'At-Risk' Session provisionally booked every Wednesday from 1000 - 1200. 
A user mailing will be sent if any work is going to take place which may impact users.

### Service Calendar

We maintain a calendar for the Cirrus service that lists upcoming events (such
as training courses and maintenance sessions):

- [Cirrus Service Calendar](calendar.html)

We keep maintenance downtime to a minimum on the service but do occaisionally
need to perform essential work on the system. Maintenance sessions are used to 
ensure that:

* software versions are kept up to date;
* firmware levels on HPE and third-party peripheral equipment are kept up to date;
essential security patches are applied;
* failed/suspect hardware can be replaced;
* new software can be installed;
periodic essential maintenance on HPE electrical and mechanical support equipment (refrigeration systems, air blowers and power distribution units) can be undertaken safely.

Additional maintenance sessions can be scheduled for major hardware or software updates; major upgrades to facility plant and infrastructure; acceptance testing following major service upgrades and statutory electrical testing.

