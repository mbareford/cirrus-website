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

## Maintenance Sessions:Quarter 2 2022 (1st April - 30th June 2022)

{% assign maintenance_2022_q2 = site.maintenance | where_exp: "maintenance", "maintenance.quarter >= '2022_q2'" %}
{% for maintenance in maintenance_2022_q2 reversed %}

    {% if forloop.first == true %}
### Quarter 2 2022 (1st April - 30th June 2022)


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

Module Update following Cirrus Upgrade March 2022 
  
| Description | Reason | Advice |
| ---    | ---  | ---   | 
| Default git loaded at login is 2.35.1 | There should be no adverse consequences for git users | 2.21 will still be available as a non-default version |
| Updated mpt	| Updated | The HPE MPI implementation (MPT) has been updated to mpt/2.25. The previous version mpt/2.22 is no longer available. Applications may require recompilation |
| Updated nvidia/cub/1.8.0 | Updated | Please use nvidia/nvhpc/22.2, which contains cub |
| Updated nvidia/cuda-11.2 | Updated | Please use nvidia/nvhpc/22.2, which contains cuda 11.6 |
| Updated nvidia/cudnn/8.2.1-cuda-11.2 | Updated | Please use nvidia/cudnn/8.2.1-cuda-11.6 |
| Updated nvidia/nvhpc	| Updated | nvidia/mathlibs-11.2 superseded by nvidia/nvhpc/22.2, which contains mathlibs cuda 11.6 |
| Updated nvidia/nvhpc-nompi	| Updated | nvidia/mathlibs-11.2 superseded by nvidia/nvhpc/22.2, which contains mathlibs cuda 11.6 |
| Remove anaconda/python2 | Outdated | Use anaconda/python3-2021.11 for python3 |
| Remove anaconda/python3-5.1.0 | Outdated | Use anaconda/python3-2021.11 for python3 |
| Remove epcc/deprecated-software	| Outdated | Deprecated with extreme prejudice |
| Remove hdf5parallel/1.10.6-intel18-mpt222 | Outdated | Please use new HDF5 module built against MPT 2.25 |
| Remove hdf5parallel/1.10.6-intel19-mpt222| Outdated | Please use new HDF5 module built against MPT 2.25 |
| Remove hdf5parallel/1.10.6-gcc6-mpt222 | Outdated	| Please use new HDF5 module built against MPT 2.25 |
| Remove htop/2.2.0	| Outdated	| Please use htop/3.1.2 |
| Remove htop/3.0.0	| Outdated | Please use htop/3.1.2 |
| Remove namd/2.12	| Outdated | Please use Superseded by namd/2.14 |
| Remove netcdf-parallel/4.7.4-intel18-mpt222	| Outdated | Depends on hdf5parallel/1.10.6-intel18-mpt222 being removed. To be replaced with proposed new NetCDF module built against MPT 2.25 |
| Remove openfoam/v1712| Outdated | Versions 2006 and 8.0 are centrally available |
| Remove openfoam/v1912| Outdated | Versions 2006 and 8.0 are centrally available |
| Remove fftw/3.3.8-intel19-mpt220| Outdated | Please use the new build against MPT 2.25 |
| Remove fftw/3.3.8-intel19-multiprecision | Outdated | Please use the new build against MPT 2.25 |
| Remove fftw/3.3.8-intel19-mpt220-multiprecision | Outdated | Please use the new build against MPT 2.25 |
| Remove fftw/3.3.8-gcc8-ompi4 | Outdated | Please use the new build against MPT 2.25 |
| Remove spack/2020 | Outdated | Update to install location has broken Spack rpaths, scripts, modules, etc. |
| Remove strace/2.2.0	| Outdated	| Use default strace/5.8 |
| Remove WRF/em_real| Not used | Not required |


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

