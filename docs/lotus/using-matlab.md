
MATLAB (Matrix Laboratory) is a multi-paradigm numerical computing environment and proprietary programming language developed by MathWorks. MATLAB allows matrix manipulations, plotting of functions and data, implementation of algorithms, creation of user interfaces, and interfacing with programs written in other languages.

MATLAB Parallel Server is installed on lotus cluster. MATLAB Parallel Server lets you scale MATLAB programs and Simulink simulations to clusters and clouds. You can prototype your programs and simulations on the desktop and then run them on clusters and clouds without recoding. MATLAB Parallel Server supports batch jobs, interactive parallel computations, and distributed computations with large matrices.

This module will add the matlab command to your PATH.

MATLAB is proprietarily licensed software.

## Available versions of the package matlab:
 Version 	| Module tags	
------------|:------------:
R2022b      |codes/matlab/R2022b
R2020b      |codes/matlab/R2020b             


## Steps for accessing matlab on HPC:

1. To load matlab, first you need to login using ssh with X11-forwarding as
```
ssh -X <username>@lotus.iittp.ac.in
```

2. Next, you need to load the matlab module as
```
module load codes/matlab/R2022b
```

## Running a MATLAB script from the command line:

A MATLAB job needs MATLAB scripts that you intend to run and a job submission script to submit it to the job scheduler.

### An Example
In this simple example, the system prints the phrase “Hello World !” in the output file.

1. The MATLAB script: HelloWorld.m

```
% display information
fprintf('Hello World !\n\n');
```
2. The job submission script: matlab_job.pbs

```
#!/bin/bash
#PBS -q cpu1h
#PBS -N test_matlab_job

##only 1 processor core is requested to test this as a serial job
#PBS -l nodes=1:ppn=1
#PBS -l walltime=00:10:00

module load codes/matlab/R2022b

cd $PBS_O_WORKDIR

matlab  -nodesktop  -nodisplay  -r  "run HelloWorld.m"

exit 0
```

3. To submit the job:
```
$ qsub matlab_job.pbs
```

4. To check the status of the job (It may show nothing if the job has been completed):
```
$ qstat -u $USER
```

5. To view the error file:
```
$ cat test_matlab_job.e[JOB ID]
```
6. To view the output file:
```
$ cat test_matlab_job.o[JOB ID]
```