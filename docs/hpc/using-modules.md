
##What is a module?
There are hundreds of people using every cluster. They all have different software needs, including conflicting versions required for different projects! How do we handle this without making a mess, or one person breaking the cluster for everyone?

This is actually a very hard, but solved within certain parameters, problem.

The answer is the standard “module” system. It allows us to have unlimited number of different software packages installed, and the user can select what they want. Modules include everything from compilers (+their required development files), libraries, and programs.

Almost like magic, we can have many versions of any software installed, and everyone can pick what they want, with no conflicts.

!!! check "Module"
    “A module lets you adjust what software is available, and makes it easy to switch between different versions.”

Software installation and management takes up a huge amount of our time, but we try to make it easy for our users. Still, it can end up taking a lot of your effort as well. If you need a program installed, we will put it in the module system.

##Knowing available modules
A few precompiled software applications and compilers/libraries are available in our HPC cluster. In order to use any applications from this list, you need to load that specific application.

To see the list of available modules, use the following command in a terminal:
``` 
module avail
```
The below command shows some meta-info of the module (name, its version, etc.)
```
module show gcc
```

##Loading modules
For example, to load the quantum espresso code,
```
module load codes/qe-6.2.1
```
Location to the compilers and libraries can be found by the following command.
```
which ifort
```
##Unloading modules
To unload a specific  module,  use the following
```
module unload codes/qe-6.2.1
```
To unload all modules,  use the following
```
module purge
```
