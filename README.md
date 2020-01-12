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

# rebootreboot
Optiona2:
Enable CentOS gui in vagrant
from: http://codingbee.net/tutorials/vagrant-tutorials/vagrant-enabling-a-vms-gui-mode

Most vagrant boxes comes without the gui desktop interface. This tutorial will show you how install and access to that gui interface.

Let’s use the standard CentOS 7 vm:

$ vagrant init centos/7
The above command will create a Vagrantfile.

Next open up the vagrant file ensure the following virtualbox setting section exists:

config.vm.provider "virtualbox" do |v|
  v.gui = true
end
Log into your vm:

$ vagrant ssh
Then switch to root:

$ sudo -i
Then install the gui desktop collection of packages:

$ yum group install 'gnome desktop'
Next switch to the gui target:

$ systemctl isolate graphical.target
You should now see the gui desktop in your virtualbox window.

Finally enable the graphical target, so that the graphical mode starts up by default on the next reboot.

$  systemctl set-default graphical.target
$ systemctl enable graphical.target
$ systemctl start graphical.target

````
##Description

##Implementation