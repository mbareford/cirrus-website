---
layout: section
title: Cirrus Hardware
summary:
---

SGI/HPE 8600 Cluster
--------------------

The Cirrus compute provision consists of 282 compute nodes connected
together by a single Infiniband fabric. 280 of these are standard 
compute nodes and 2 of these contain 4 GPU accelerators.

Cirrus Phase II saw the addition of 36 HPE Plainfield Blades each with two Intel 
Xeon processors and four NVIDIA v100 GPUs. A 512 TB (raw) of NVMe fast storage for 
data intensive applications on Cirrus was also added. 

There are 3 login nodes that share a common software environment and
file system with the compute nodes.

### Compute Nodes

#### CPU compute nodes

Cirrus standard compute nodes each contain two 2.1 GHz, 18-core Intel Xeon
E5-2695 (Broadwell) series processors. Each of the cores in these
processors support 2 hardware threads (Hyperthreads), which are enabled
by default.

The standard compute nodes on Cirrus have 256 GB of memory shared between the two
processors. The memory is arranged in a non-uniform access (NUMA) form:
each 18-core processor is a single NUMA region with local memory of 128
GB. Access to the local memory by cores within a NUMA region has a lower
latency and higher bandwidth than accessing memory on the other NUMA region.

There are three levels of cache, configured as follows:

-   L1 Cache 32 KiB Instr., 32 KiB Data (per core)
-   L2 Cache 256 KiB (per core)
-   L3 Cache 45 MiB (shared)

There are 280 standard compute nodes on Cirrus giving a total of 10,080 cores.
When employing hyperthreads, the core count doubles to 20,160.

#### GPU compute nodes

The Cirrus Phase II GPU nodes added 36 GPU compute nodes which each contain two 2.5 GHz, 
20-core Intel Xeon Gold 6148 (Cascade Lake) series processors. Each of the cores in these 
processors support 2 hardware threads (Hyperthreads), which are enabled by default. 
The nodes also each contain four NVIDIA Tesla V100-SXM2-16GB (Volta) GPU accelerators connected 
to the host processors and each other via PCIe. These GPU compute nodes provide a total of 144 
GPU accelerators and 1440 CPU cores.

There are also two Cirrus GPU compute nodes which each contain two 2.4 GHz, 20-core Intel 
Xeon Gold 6248 (Skylake) series processors. Each of the cores in these processors support 
2 hardware threads (Hyperthreads), which are enabled by default. The nodes also each contain 
four NVIDIA Tesla V100-SXM2-16GB (Volta) GPU accelerators connected to the host processors and
each other via PCIe. These GPU compute nodes provide a total of 8 GPU accelerators and 80
CPU cores.

All of the GPU compute nodes on Cirrus have 384 GB of main memory shared between the two 
processors. The memory is arranged in a non-uniform access (NUMA) form: 
each 20-core processor is a single NUMA region with local memory of 192
GB. Access to the local memory by cores within a NUMA region has a lower
latency and higher bandwidth than accessing memory on the other NUMA region.

There are three levels of cache, configured as follows:

-   L1 Cache 32 KiB Instr., 32 KiB Data (per core)
-   L2 Cache 1 MiB (per core)
-   L3 Cache 27.5 MiB (shared)

Each GPU accelerator has 16 GiB of fast GPU memory.


Infiniband fabric
-----------------

The system has a single infiniband (IB) fabric and every compute node
and login node has a single ib0 interface. The IB interface is FDR, with
a bandwidth of 54.5 Gb/s. The Lustre servers have two connections to the
IB fabric and all Lustre file system IO traverses the IB fabric.

File systems and Data Infrastructure
-----------------------------------

There are a number of file systems available on Cirrus:

* 1.5 PiB Ceph distributed file system for critical data storage. Mounted on all login nodes. Backed up.
* 24 PiB HPE E1000 ClusterStor Lustre parallel file system provides
  high performance data access with high capacity. Mounted on all login and compute nodes. Not backed up.
* 233 TiB HPE high performance solid state storage. Mounted on all login and compute nodes. Not backed up.

The compute nodes are diskless. Each node boots from a cluster
management noded called the Rack Leader and NFS mounts the root file
system from this management node.

Parallel I/O
------------

For a description of the terms associated with Lustre file systems
please see the description on Wikipedia:

-   [Lustre File Systems
    Description](https://en.wikipedia.org/wiki/Lustre_(file_system))

The default striping on the Lustre filesystem is 1 stripe, and the
default stripe size is 1 MiB.

