Ansys HPC software suite is installed on lotus cluster. The various Ansys HPC licensing options allow users to scale to whatever computational level of simulation they require,performing more complex and accurate simulations in less time.

Available Ansys modules: Ansys Mechanical, Ansys CFD, Ansys Electronics

Below are the steps for accessing Ansys workbench on HPC:

To load Ansys workbench, first you need to login using ssh with X11-forwarding as
```
ssh -X 10.21.130.19
```

Then you need to load the Ansys workbench module as
```
module load codes/ansys-wb2
```
then execute the following command to access Ansys workbench.
```
runwb2
```

You should run your simulation in a queue but not on master node where you logged in.
