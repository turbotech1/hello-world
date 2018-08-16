# hello-world
Break the ice with github. Well linux and its power sometimes requires a little bit to get things in place to achieve a reliable and stable outcome. It was a long ago that I have used Vnc server to access a linux desktop GUI . It used to be quite straight forward . I am going to go through the process to get it running stable on ubuntu linux 18.04 LTS

Operating System and Software Versions
Operating System: - Ubuntu 18.04 Bionic Beaver
Requirements
Privileged access to your Ubuntu System as root or via sudo command is required.
Difficulty
MEDIUM
Conventions

# - requires given linux commands to be executed with root privileges either directly as a root user or by use of sudo command
$ - requires given linux commands to be executed as a regular non-privileged user

Instructions
Ubuntu VNC server setup
Let's start by the installation of the VNC server and the Xfce desktop manager core files:

$ sudo apt install vnc4server xfce4 xfce4-goodies

Once the VNC server is installed we can begin the configuration by setting up a user password to be used by a VNC client when creating a remote connection:

$ vncpasswd


Next, create the ~/.vnc/xstartup file to start the Xfce4 desktop:

$ mkdir ~/.vnc
$ nano ~/.vnc/xstartup

Insert the the following content and save:

#!/bin/bash
startxfce4 &


Lastly, make the ~/.vnc/xstartup file executable:
$ chmod +x ~/.vnc/xstartup

At this stage we are ready to start the VNC server. For this simply run the vncserver command from your home directory:

$ vnc4server

New 'ubuntu:1 (linuxconfig)' desktop is ubuntu:1

Starting applications specified in /home/linuxconfig/.vnc/xstartup
Log file is /home/linuxconfig/.vnc/ubuntu:1.log
