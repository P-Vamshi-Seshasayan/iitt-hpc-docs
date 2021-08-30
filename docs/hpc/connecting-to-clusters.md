# Connecting to the clusters
## Connecting via ssh
The traditional way of interacting with a cluster is via a terminal, and Secure Shell (ssh) is the most common way of doing that.

To connect to Lotus cluster:
```
ssh username@10.21.130.19
```

To connect to Lotus and run graphical applications:
```
ssh -X username@10.21.130.19
```

To connect to Orchid cluster:
```
ssh username@10.21.131.252
```

##SSH Software
**Linux:**
All Linux distributions come with an ssh client, so you don’t need to do anything. To use graphical applications, use the standard -X option, nothing extra needed.

**Mac:**
ssh is installed by default, same as Linux. Run it from a terminal, same command as Linux. To run graphical applications, you need to install an X server (XQuartz).

**Windows:**
You can use the PowerShell for ssh same as in Linux, or you need to install a ssh client yourself: PuTTY is the standard one. If you want to run graphical programs, you need an X server on Windows like MobaXterm.
