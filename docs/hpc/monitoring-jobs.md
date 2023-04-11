## Monitoring the status of a job
* To check the current jobs of a user: ```qstat -u <username>``` OR for current user ```qstat -u $USER```
* The command qstat shows what jobs are currently submitted or running on the queuing system. ```qstat -ans```
* The command ```qstat -q``` shows which queues are available.
* With ```qstat -f``` the full output of the job is displayed.
* To view job status and job events a job: ```tracejob <jobid>>```
* To check more details about the submitted job: ```qstat -f <jobid>```

## Deleting a job
An already submitted job can be deleted using the qdel command. To cancel a submitted job use ```qdel <jobid>```
Multiple space-separated job IDs can be specified

