# Create Vagrant file to create vm centos/ with desktob GNUM
## Installation 
````
vgrant up
Optional: Run the following command to list down the available package groups for CentOS 7.

# yum group list
Step 1: Install Gnome GUI packages using the YUM command.

CentOS 7:

# yum groupinstall "GNOME Desktop" "Graphical Administration Tools"
Step 2: Enable GUI on system startup. In CentOS 7 / RHEL 7,  systemd uses “targets” instead of runlevel. The /etc/inittab file is no more used to change run levels. So, issue the following command to enable the GUI on system start.

# ln -sf /lib/systemd/system/runlevel5.target /etc/systemd/system/default.target
Step 3: Reboot the machine to start the server in the graphical mode.

# reboot
````
##Description

##Implementation