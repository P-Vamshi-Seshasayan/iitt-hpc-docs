
#Building Software from source code

Users are able to compile and install the software they need on the HPC Cluster. Software should be installed to your ```/home/username``` directory. 

Irrespective of the actual method of installation, at core the installation process involves putting the installed software in a directory in your ```$HOME``` directory and telling it where it can find all the software and libraries that it depends on.

This document gives the gist of one of to the most common way to build software from source code. Compiling software from source often involves the following steps:


Compiling from source may be the only option to install software on HPC. The HPC has necessary compilers to facilitate compilation of most software. Follow the steps to know how to compile and install software from source.

##Download the Source Code and Unpack it

The source code for software on Linux comes in the form of compressed tar files, which typically have either .tar.gz or .tar.bz2 extensions. The tools that are used for packing the source code into these tar balls are ‘tar’ (used for combining multiple files into one), ‘gzip’ or bzip2 (used for compression). To fetch the source code tarball for a particular software you need to know the URL to the tarball.

Once you have the download link, use ‘wget’ to fetch the tarball from command line. wget command is very flexible and has lot of options. The below command will download the tarball into the current directory. 

```$ wget <link to the tarball>``` 

Next you needs to unpack the tarball in order to get access to the source code and other files:

```$ tar -xvfz <name of tarball>```

##Read Install Documentation

Once the software source code is downloaded and extracted, the very first thing that one should do is to go through the documentation. This may sound boring to most of us but this is a very important step as doing this step thoroughly would save you from most of the future problems. The documentation provides information about the software, changes since last version, links to more documentation, information regrading the author of the software, steps for compilation and installation of software etc. So we can see that lots of valuable information is present in the documentation.

This whole information is broadly divided into two files : ‘README’ and ‘INSTALL’. 

While ‘INSTALL’ covers all the information required for compilation and installation, all the other information is covered in the ‘README’ file. Please note that the name of file and its case may vary.


##Configuration

Once the above step is over then we can assume that we have sufficient theoretical knowledge about this software and now we can move forward and configure the environment for compiling and installing the software on our system. Most of the packages come along with a configuration script that can be used for configuring the environment. The file name for configuration file is mostly ‘configure’. This script usually accepts parameters that can be used to control some features of this software. Also this script makes sure that all the tools required for compilation are present in the system.

To learn about the options provided by a specific configuration file, run the following command: 

```$ configure --help``` 

To start configuring the build environment, execute the following command : 

```$ ./configure --prefix=/home/user/bin```

!!! attention
    ```username``` in ```/home/username/bin``` represents the username of the user installing the software. Example: ```/user/vamshi/bin```

The prefix argument in the above command tells the system where to install the compiled binaries. If you did not set prefix argument, the system will try to install your software in root directories and you will get "Permission Denied" error.

The above command will check and/or create the build environment and if everything goes fine then it produces a file called ‘makefile’. The file ‘makefile’ is used in the compilation of the software.

##Compilation

Once the makefile is generated, then in the same directory just run the following command: ```$ make``` 
The above command will compile all the source code related to the software. If compilation encounters some problem then error is thrown on the console. This may take some time depending on the software being installed.

!!! important
    Make sure to load the needed modules before compiling and to load the same modules in your job submission.

##Installation

Once the compilation is done successfully then all the required binaries are created. Now is the time to install these binaries in the standard paths so that they can be invoked from anywhere in the system. To do this run the following command : 

```$ make install```

The above command will install your software at /home/username/bin directory. 

Note that the INSTALL file may ask you to run this as root or using sudo, however, since you are installing in your home directory, it is not required.