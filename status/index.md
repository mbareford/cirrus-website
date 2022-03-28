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
- [Module Updates](#module-updates)
- [Service Calendar and Maintenance](#service-calendar-and-maintenance)

## Thursday 17th March 1530: Return to Service

The upgraded Cirrus service has now been returned to service.
There are a reduced number of nodes available 220/280 CPU nodes while HPE continue to investigate an issue. We hope to return all nodes to service by next week. 

The management system software was updated as well as the operating system on the compute and login nodes. There is a new CEPH /home file system available and we hope to have the new /work file system available in the summer. 

Please contact support@cirrus.ac.uk if you have any questions or require assistance and apologies for any inconvenience caused by the delay to return to service.

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
| Resolved | Issue | 2022-03-28 16:50 | 2022-03-28 16:53 | Cirrus | Users logged out of login node 1. | Login node 1 shut down due to operator error. Users can reconnect and will be automatically directed to other login nodes. | 
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

