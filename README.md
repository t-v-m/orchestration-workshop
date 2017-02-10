Orchestration Worshop Starter VMs
=================================
This is a simple Vagrant setup which will get 5 blank Virtualbox VMs setup with one command. All the boxes run ubuntu/trusty64.
## VMs included
+ Provisioner - Used to provision the other boxes with Chef, Ansible or any other orchestration + tool. Probably not needed if you are on a Mac or Linux.
+ Balancer - Load balancer for the 2 web servers
+ Web Server 1 - The 2 web servers
+ Web Server 2 - The 2 web servers
+ Database - The database server
## Prerequisites
[Vagrant](https://www.vagrantup.com/) and [Virtualbox](https://www.virtualbox.org/)
If you have issues make sure you are on the latest version of both.
## Installation
1. Copy the Vagrantfile into a folder on your computer.
2. Open up a terminal window and CD into the directory where the Vagrantfile is.
3. Run *vagrant up*
It will download the ubuntu box which will take a few minutes but it is only done once. From there it will provision each of the VMs which can also take about 5 minutes.

The private IP addresses for the boxes are as follows.
+ Provisioner - 192.168.10.21
+ Balancer - 192.168.10.22
+ Web Server 1 - 192.168.10.23
+ Web Server 2 - 192.168.10.24
+ Database - 192.168.10.25

## SSH
ssh vagrant@[ip_address]

eg. ssh vagrant@192.168.10.21

The password is *vagrant* if it asks.