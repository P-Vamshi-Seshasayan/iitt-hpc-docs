# Lotus Cluster

## Introduction
IIT Tirupati has set up a High Performance Computing Cluster (HPC), Lotus, in 2019. The Lotus cluster provides advanced computational resources for IIT Tirupati faculty and students to perform computational research on campus. The system provides high performance, big data, and graphical processing unit (GPU) computing for research groups spanning multiple disciplines.

## System Configuration
The Lotus cluster is made up of 2 master nodes, 24 compute nodes and 2 GPU nodes running on RHEL 7 that take and process jobs submitted from the master node using the PBS Pro job scheduler.

Each node has Intel(R) Xeon(R) Gold 6126 CPU @ 2.60GHz with 24 cores, 96GB RAM. Lotus cluster uses Lustre parallel file system for fast IO, and Infiniband network for computational interconnect. 

Totally, the cluster has 624 CPU cores, 2 TB RAM, 100TB PFS (Lustre storage), and 2 x Nvidia Tesla V100 16GB GPUs. 

## Queues

There are 7 Queues - cpu15d, cpu7d, cpu3d, cpu2d, cpu1d, cpu1h, and gpu4d, with appropriate resources grouped together. Details are below:

 Queue Name | No. of nodes | No. of cores | Max. Queue Time 
------------|:------------:|:------------:|:---------------:
cpu15d      |4             | 96           | 15 days
cpu7d       |4             | 96           | 7 days
cpu3d       |8             | 192          | 3 days
cpu2d       |5             | 120          | 2 days
cpu1d       |2             | 48           | 1 day
cpu1h       |1             | 24           | 1 hour
gpu4d       |2             | 48           | 4 days

## Software – Compilers, Libraries, Applications

### GNU compilers

C = /usr/bin/gcc
C++ = /usr/bin/g++
FORTRAN = /usr/bin/gfortran, /usr/bin/f95

### Intel MPI (Parallel) compilers

mpiicc = /apps/intel/parallel_studio_xe_2019.5.075/compilers_and_libraries_2019/linux/mpi/intel64/bin/mpiicc
mpiicpc = /apps/intel/parallel_studio_xe_2019.5.075/compilers_and_libraries_2019/linux/mpi/intel64/bin/mpiicpc
mpiifort = /apps/intel/parallel_studio_xe_2019.5.075/compilers_and_libraries_2019/linux/mpi/intel64/bin/mpiifort

### Applications:

Application |Location
------------|:------------
GROMACS     |/apps/codes/gromacs
LAMMPS      |/apps/codes/lammps
Quantum Espresso|/apps/codes/qe
VASP        |/apps/codes/vasp
NAMD        |/apps/codes/NAMD
Gaussian    | /etc/profile.d/gaussian.sh
NWChem      |/apps/codes/nwchem
SIESTA      |/apps/codes/siesta-netcdf
BerkeleyGW  |/apps/codes/
CPMD        |/apps/codes/CPMD_ompi
CP2K        | /apps/codes/CP2k
Packmol     |/apps/codes/packmol
Vmd         |/usr/local/bin/vmd
P4vasp      |/apps/codes/p4vasp
Vesta       |/apps/codes/VESTA
OVITO       |/apps/codes/ovito
ANSYS       |/apps/codes/
Xcrysden    |/apps/codes/xcrysden
Gnuplot     |/usr/bin/gnuplot
Xmgrace     |/apps/codes/xmgrace

## Utilization
[View Resource Utilization <small>^:octicons-link-external-16:^</small>]()