## Transferring files between local machine and HPC cluster
Users are advised to keep a copy of their data with themselves, once the project/research work is completed by transferring the data in from the cluster to their local system (laptop/desktop).
### Transferring files using SCP:
#### Linux
scp –r <path to the local data directory> <your username>@<IP of the lotus/orchidcluster>:<path to directory on HPC where to save the data>

As an example, the file filename will be copied to/from the user's storage directory on Lotus cluster using SCP.

From the local machine, open a terminal window and use SCP.
**Local to Lotus cluster**
```
scp filename user_name@10.21.130.19:/storage/user_name/
```

**Lotus cluster to local**
```
scp user_name@10.21.130.19:/storage/user_name/filename .
```
There will be a prompt for a password(s).

#### Windows
* If you prefer GUI, Use WinSCP:
  This popular tool is freely available and is used very often to transfer data from Windows machine to Linux machine. This tool is GUI based which makes it very user-friendly.
Link for this tool is :   https://winscp.net/eng/download.php
* If you prefer commandline, you can use pscp (part of putty tools)/MobaXterm

### Download files from the internet using wget
One of the most straightforward ways to download files is to use wget. Any file that can be downloaded in your web browser with an accessible link can be downloaded using wget. This is a quick way to download datasets or source code.

The syntax is: 
```
wget https://some/link/to/a/file.tar.gz.
``` 