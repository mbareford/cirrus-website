---
layout: section
title: Cirrus Service Status
summary: Up to date status of the Cirrus service
---

 ## Current System Load

 ### Monday 21st February - Monday 14th March 
 
 The Cirrus Service will be upgraded from Monday 21st February - Monday 14th March but users will be notified if we are able to return the system earlier. During this time, the Cirrus Service will be unavailable. This means that users will not be able to connect to the Cirrus login nodes, run jobs or access any data stored on Cirrus. Any jobs that are in the batch system queue will be removed.

There will be new storage arrangements when the system is returned to users and these will be detailed in further user messages before the system is returned alongside updated documentation.

&nbsp;

- [Current System Load](#current-system-load)
- [Known Issues](#known-issues)
- [Current Issues](#current-issues)
- [Recent Issues](#recent-issues)
- [Service Calendar and Maintenance](#service-calendar-and-maintenance)


## Current System Load

The plot below shows the status of the CPU nodes on the current Cirrus service for the past day
(note: the Cirrus GPU nodes are not included in this plot).

A description of each of the status types is provided below the plot.

![Cirrus Node Status graph](https://safe.epcc.ed.ac.uk/Graphs/cirrus.png)
{: style="width=80%" align="center"
alt="Cirrus Node Status over time" 
title="Cirrus Node Status over time"}

- *alloc*: Nodes running user jobs
- *idle*: Nodes available for user jobs
- *resv*: Nodes in reservation and not available for standard user jobs
- *down*, *drain*, *maint*, *drng*, *comp*: Nodes unavailable for user jobs
- *mix*: Nodes in multiple states 

Note: the long running reservation visible in the plot corresponds to the *short* QoS which
is used to support small, short jobs with fast turnaround time.


## Known Issues 

We are experiening a heavy load on the metadata server. Our systems team are investigating but we suspect this is due to user(s) performing many I/O operations. We apologise for the inconvenience this is causing users. 

## Service Alerts

| Status | Type | Start | End | System | User Impact | Reason |
| ---    | ---  | ---   | --- | ---    | ---         | ---    |
| Ongoing | Issue | 2021-07-01 0900 | tbc | Object Store (WoS) | The WoS is currently unavailable. | We are working with the hardware vendor to restore the WoS to service again. |   

### Recently Resolved Service Alerts

| Status | Type | Start | End | System | User Impact | Reason |
| ---    | ---  | ---   | --- | ---    | ---         | ---    |
| Resolved | Issue | 2022-01-09 10:00 | 2022-01-10 10:30 | Cirrus, SAFE | Outgoing network access from Cirrus to external sites was not working. SAFE response was slow or degraded. | DNS issue at datacentre |
| Resolved | Issue | 2021-11-05 0800  | 2021-11-05 1130 | Cirrus: CPU compute nodes | A small number of CPU compute nodes were unavailable to run jobs | A power incident in the Edinburgh area caused a number of CPU compute nodes to lose power. |  
| Resolved | Issue | 2021-10-28 1130  | 2021-10-28 1600 | Cirrus | Some external connections are unavailable such as git pull, pushes, licence servers | Network changes at the ACF have caused issues. The University network team have resolved the issues. |    


## Service Calendar and Maintenance

## Maintenance Sessions:Quarter 1 2022 (1st January - 31st March 2022)

| Status | Type | Start | End | System | User Impact | Reason |
| ---    | ---  | ---   | --- | ---    | ---         | ---    |
| Planned | Full Maintenance | 2022-02-21  0900 | 2022-03-11 1700 | Cirrus | There will be a full rebuild of the Cirrus Service. It will be unavailable during maintenance session. | Attach new storage storage, bring the system software up to date. |


## Maintenance Sessions:Quarter 4 2021 (1st Oct - 31st December 2021)

| Status | Type | Start | End | System | User Impact | Reason |
| ---    | ---  | ---   | --- | ---    | ---         | ---    |
| Planned | Outage | 2021-12-01  0900 | 2021-12-01 1700 | Cirrus | Full system will be unavailable during maintenance session. | Third-party maintenance on cooling system. |
| Completed | At-Risk | 2021-10-27 0900 | 2021-10-27 1700 | Cirrus | Period of up to 30mins when external connections are not possible. Compute nodes will continue to run jobs. | Network upgrade at the Advanced Computing Facility (ACF) |

## Regular Module Updates 

On Wed 15 Dec 2021 we updating modules on Cirrus as detailed below.
  
| Description | Reason | Advice |
| ---    | ---  | ---   | 
| Default git loaded at login to be updated to 2.27 | There should be no adverse consequences for git users | 2.21 will still be available as a non-default version |
| Remove starccm+/12.04 | Outdated | Please Use a later version |
| Remove starccm+/12.04.011-R8 | Outdated | Please Use a later version |
| Remove starccm+/13.06.012	| Outdated | Please Use a later version |
| Remove starccm+/13.06.012-R8 | Outdated | Please Use a later version |
| Remove starccm+/14.04.013-R8 | Outdated | Please Use a later version |
| Remove starccm_/14.06.013-R8 | Outdated	| Please use a later version |
| Remove gnu-parallel/20170322-gcc6	| Outdated	| Use later version |
| Remove matlab/R2018b	| Outdated | Please use a later version |
| Remove flacs/10.9.1	| Outdated | Please use a later version |
| Remove strace/2.2.0	| Old	| Use default strace/5.8 |

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

