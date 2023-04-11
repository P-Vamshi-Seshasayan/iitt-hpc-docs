## 
We use PBS PRO Community Edition software as the workload manager. PBS is a workload management and job scheduling system to manage computing resources, and was originally developed at NASA in the 1990s. 

PBS Pro job scripts are used to submit and execute jobs. The user puts values into a job script for the resources being requested, such as the number of processors to be used, the memory to be used, or number of nodes required. Other values are also set for the runtime parameters and application-specific variables. 

The steps for running a job through a PBS Pro job script are:
1. Creating an application to be run via the job script 
2. Creating the job script, adding directives, applications, runtime parameters, and application-specific variables to the script 
3. Submitting the script to the workload management system

A job script in PBS Pro has a structure illustrated by the following basic example:
```
#!/bin/bash
#PBS -N Job Name
#PBS -l nodes=2:ppn=24 ## used in older PBS versions
#PBS -o out.log
#PBS -q cpu7d
cd $PBS_O_WORKDIR
mpirun -np 48 program executable inputfile > outputfile
```
This job script request 2 nodes and 24 cores from each node using cpu7d queue. So total 48 cores are used for running the job. 

Another sample job script:
```
#!/bin/bash 
#PBS -l walltime=1:00:00
#PBS -l select=2:ncpu=1:mem=500mb ## used in newr]er PBS versions (orchid)
#PBS -j oe 
cd ${HOME}/myprogs 
mpirun myprog a b c
```
The first line is the standard “shebang” line used for scripts. 
The lines that start with #PBS are PBS Pro directive lines (#  PBS is a comment)
The last two lines are an example of setting any remaining options or configuration settings up, so that the script can run. In this case, a change to the directory myprogs is made, and then the executable myprog is run, with arguments a b c. 
The line that runs the program is called the executable line

There are several PBS directives. A few useful are below:
#PBS -N ExampleJob - sets the name of the job to ExampleJob. Output and Error Files will be generated with this name.
#PBS -q workq - this directive specifies the queue in which the job should run.
#PBS -M  vamshi@iittp.ac.in - using this directive you can get  the job details to the specified email address at the beginning and termination of the job.

Walltime Directive
The workload manager typically has default walltime limits per queue with a value limit set by the administrator. The user can set a walltime limit for the job by setting the ”#PBS -l walltime” directive to a specific time. The time specified is the maximum time that the user expects the job should run for, and it allows the workload manager to work out an optimum time to run the job. The job can then run sooner than it would by default. 
If the walltime limit is exceeded by a job, then the job is stopped, and an error message in the following format is displayed:
=>> PBS: job killed: walltime exceeded limit Here, is the time that the job actually took to run after it ran, while is the time that the user set as the walltime resource limit.

So to avoid waiting a very long time, the user really should set a walltime.

Job Output 
By default, the output from the job script goes into the current working directory for PBS Pro. By default, error output is written to .e and the application output is written to .o, which is a unique number that the workload manager allocates. Specific output and error files can be set using the -o and -e options respectively. The error and output files can usefully be concatenated into one file with the -j oe or -j eo options. More details on this can be found in the qsub man page.

Monitoring the status of a job
The command qstat shows what jobs are currently submitted or running on the queuing system.
Example: qstat -ans

The command qstat -q shows which queues are available.

With qstat -f the full output of the job is displayed.

Deleting a job
An already submitted job can be deleted using the qdel command: 
qdel <job-id>
Multiple space-separated job IDs can be specified
