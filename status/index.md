---
layout: section
title: Cirrus Service Status
summary: Up to date status of the Cirrus service
---

&nbsp;

- [Current System Load](#current-system-load)
- [Known Issues](#known-issues)
- [Current Issues](#current-issues)
- [Recent Issues](#recent-issues)
- [Service Calendar and Maintenance](#service-calendar-and-maintenance)

## Friday 11th March: Cirrus Upgrade Status and Delayed Return to Service

Unfortunately, there was a delayed start to the upgrade process due to hardware issues on Cirrus. The hardware issues have been resolved and the teams have been making good progress with the Cirrus upgrade. The cluster management software has been upgraded and the operating system on the login and compute nodes has also been upgraded. The EPCC systems team are now making our local customisations to Cirrus in parallel to final work by HPE. The Computational Science and Engineering (CSE) team are also testing the programming environment and will rebuild any application software where needed.

The new CEPH storage is now attached to Cirrus and further details of the new storage arrangements will be sent via a user mailing and will be fully documented on the Cirrus website.

Given the delayed start to the upgrade process, we are not able to reopen the service on Monday 14th March as previously advertised. We will send a further user mailing on Wednesday 16th March where we hope to confirm the return to service time and do apologise for the delay in return to service.

## Cirrus Upgrade: Monday 21st February - Monday 14th March 
 
The Cirrus Service will be upgraded from Monday 21st February - Monday 14th March but users will be notified if we are able to return the system earlier. During this time, the Cirrus Service will be unavailable. This means that users will not be able to connect to the Cirrus login nodes, run jobs or access any data stored on Cirrus. Any jobs that are in the batch system queue will be removed.

There will be new storage arrangements when the system is returned to users and these will be detailed in further user messages before the system is returned alongside updated documentation.


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
| Planned | Full Maintenance | 2022-02-21  0900 | 2022-03-16 1700 | Cirrus | There will be a full rebuild of the Cirrus Service. It will be unavailable during maintenance session. | Attach new storage storage, bring the system software up to date. |


## Maintenance Sessions:Quarter 4 2021 (1st Oct - 31st December 2021)

| Status | Type | Start | End | System | User Impact | Reason |
| ---    | ---  | ---   | --- | ---    | ---         | ---    |
| Planned | Outage | 2021-12-01  0900 | 2021-12-01 1700 | Cirrus | Full system will be unavailable during maintenance session. | Third-party maintenance on cooling system. |
| Completed | At-Risk | 2021-10-27 0900 | 2021-10-27 1700 | Cirrus | Period of up to 30mins when external connections are not possible. Compute nodes will continue to run jobs. | Network upgrade at the Advanced Computing Facility (ACF) |

## Regular Module Updates 

Module Update following Cirrus Upgrade March 2022 
  
| Description | Reason | Advice |
| ---    | ---  | ---   | 
| Default git loaded at login is 2.35.1 | There should be no adverse consequences for git users | 2.21 will still be available as a non-default version |
| Updated mpt	| Updated | The HPE MPI implementation (MPT) has been updated to mpt/2.25. The previous version mpt/2.22 is no longer available. Applications may require recompilation |
| Updated nvidia/nvhpc	| Updated | Version 22.2 (February 2022) has been added, supporting CUDA 11.6. The default is now the latest available version on the system. Versions 21.9 and 21.2 are still available (default was 21.2), but the latest version is recommended. Applications may require re-compilation. |
| Updated nvidia/nvhpc	| Updated | Version 22.2 (February 2022) has been added, supporting CUDA 11.6. The default is now the latest available version on the system. Versions 21.9 and 21.2 are still available (default was 21.2), but the latest version is recommended. Applications may require re-compilation. |
| Remove anaconda/python2 | Outdated | Use anaconda/python3-2021.11 for python3 |
| Remove anaconda/python3-5.1.0 | Outdated | Use anaconda/python3-2021.11 for python3 |
| Remove epcc/deprecated-software	| Outdated | Deprecated with extreme prejudice |
| Remove hdf5parallel/1.10.6-intel18-mpt222 | Outdated | Please use new HDF5 module built against MPT 2.25 |
| Remove hdf5parallel/1.10.6-intel19-mpt222| Outdated | Please use new HDF5 module built against MPT 2.25 |
| Remove hdf5parallel/1.10.6-gcc6-mpt222 | Outdated	| Please use new HDF5 module built against MPT 2.25 |
| Remove htop/2.2.0	| Outdated	| Please use htop/3.1.2 |
| Remove htop/3.0.0	| Outdated | Please use htop/3.1.2 |
| Remove spack/2020 | Outdated | Update to install location has broken Spack rpaths, scripts, modules, etc. |
| Remove WRF/em_real| Not used | Not required |
| Remove openfoam/v1712| Outdated | Versions 2006 and 8.0 are centrally available |
| Remove openfoam/v1912| Outdated | Versions 2006 and 8.0 are centrally available |
| Remove fftw/3.3.8-intel18| Outdated | Please use the new build against MPT 2.25 |
| Remove fftw/3.3.8-intel19-mpt220| Outdated | Please use the new build against MPT 2.25 |
| Remove fftw/3.3.8-intel19-multiprecision | Outdated | Please use the new build against MPT 2.25 |
| Remove fftw/3.3.8-intel19-mpt220-multiprecision | Outdated | Please use the new build against MPT 2.25 |
| Remove fftw/3.3.8-gcc8-ompi4 | Outdated | Please use the new build against MPT 2.25 |
| Remove strace/2.2.0	| Old	| Use default strace/5.8 |


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

