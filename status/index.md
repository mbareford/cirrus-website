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

| Status | Type | Start | End | System | User Impact | Reason |
| ---    | ---  | ---   | --- | ---    | ---         | ---    |
| Ongoing | Issue | 2021-10-28 1130 BST | 2021-10-28 tbc | Cirrus | Some external connections are unavailable such as git pull, pushes, licence servers | Network changes at the ACF have caused issues. The University network team are working to resolve these. |   
| Ongoing | Issue | 2021-07-01 0900 | tbc | Object Store (WoS) | The WoS is currently unavailable. | We are working withthe vendor to restore the WoS to service again. |   

### Current Issues

No Current Issues

### Recent Issues

No recent issues

## Service Calendar and Maintenance

## Maintenance Sessions:Quarter 4 2021 (1st Oct - 31st December 2021)

| Status | Type | Start | End | System | User Impact | Reason |
| ---    | ---  | ---   | --- | ---    | ---         | ---    |
| Planned | At-Risk | 27/10/21 0900 | 27/10/21 1700 | Cirrus | Period of up to 30mins when external connections are not possible. Compute nodes will continue to run jobs. | Network upgrade at the Advanced Computing Facility (ACF) |
| Planned | Outage | 03/11/21 0900 | 03/11/21 1700 | Cirrus | Full system unavailable during maintenance session. | Third-party maintenance on cooling system. |


### Wednesday 8th September 
#### Modules Deletions


As part of our regular maintenance of the Cirrus Service, we would like to remove outdated, broken or unused modules.

| Module |  | 
| ---    | ---  | 
| ansys/17.2 |Please use later version |  
| ansys/19.2 | Please use later version | 
| ansys/2020R1 | Please use later version | 
| Intel 19.0.0.117 | Please use intel-19.5 or later. | 
| matlab/R2018a	|  Please use later version |
| nvidia/cuda-10.1 | Please use the latest NVIDIA HPC SDK. See "module avail nvidia/nvhpc" for current versions.|
| nvidia/cuda-10.2	| Please use the latest NVIDIA HPC SDK. See "module avail nvidia/nvhpc" for current versions. |
| nvidia/cuda-11.0	| Please use the latest NVIDIA HPC SDK. See "module avail nvidia/nvhpc" for current versions.|
| nvidia/mathlibs-10.1	| Please use the latest NVIDIA HPC SDK. See "module avail nvidia/nvhpc" for current versions.|
| nvidia/mathlibs-10.2	| Please use the latest NVIDIA HPC SDK. See "module avail nvidia/nvhpc" for current versions.|
| nvidia/compilers-20.9	| Please use the latest NVIDIA HPC SDK. See "module avail nvidia/nvhpc" for current versions.|
| nvidia-compilers-mpi-20.9	| Please use the latest NVIDIA HPC SDK. See "module avail nvidia/nvhpc" for current versions.|
| openmpi/4.0.3	      | Please use openmpi/4.1.0 |
| openmpi/4.0.3-gcc8	| Please use openmpi/4.1.0 |
| openmpi/4.0.5-ucx	| Please use openmpi/4.1.0 |
| openmpi/4.1.0-cuda	| Please use openmpi/4.1.0-cuda-11.2 |
| openmpi/4.1.0-cuda-10.1	| Please use openmpi/4.1.0-cuda-11.2 |
| openmpi/4.1.0-cuda-10.2	| Please use openmpi/4.1.0-cuda-11.2 |
| openmpi/4.1.0-ucx-gcc8	| Please use openmpi/4.1.0 |
| R/3.4.0	| Please use later version |
| singularity/3.6.1	| Please use singularity/3.7.2 (`--with-setuid` install) |
| singularity/3.7.0	| Please use singularity/3.7.2 (`--with-setuid` install) |
| singularity/3.7.1	| Please use singularity/3.7.2 (`--with-setuid` install) |
| miniconda3/4.9.2-py38    | Please use miniconda3/4.9.2-gpu |
| miniconda3/4.9.2-py38-torch    | Please use miniconda3/4.9.2-gpu-torch |
| miniconda3/4.9.2-py38-tensorflow    | Please use miniconda3/4.9.2-gpu-tensorflow |

Please get in touch by Wednesday 1st September if you have an issue with any module being removed.
<!--There are regular 'At-Risk' maintenance sessions on Wednesdays from 1000-1200. -->

## Completed Maintenance Sessions
### Wednesday 18th August 

The networking maintenance has now been completed successfully at the Advanced Computing Facility (ACF). 

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

