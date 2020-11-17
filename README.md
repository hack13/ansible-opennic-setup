# OpenNIC Setup with Ansible
This is a simple Ansible Script to use to setup an OpenNIC server with Ansible. It
currently supports CentOS 7, Fedora 28 through 33, and Ubuntu 18.04 LTS. I do plan to add Debian and Ubuntu 20.04 support in the
future. It is also an open project, so feel free to fork and make your own changes.
I also welcome feedback.

# How To Use
On your local machine(or your Ansible host), and update your /etc/ansible/hosts like below updating with the IP Addresses of your servers:
```
[opennic]
xxx.xxx.xxx.xxx
xxx.xxx.xxx.xxx
```
Once you have added the hosts to your ansible hosts file, run the following command in the directory you have dropped this playbook:
```
ansible-playbook opennic-setup.yml
```

# Notes For Each OS

## CentOS 7
* Installs and configures Firewalld
* Installs and configures Named
* Configures SELinux to allow Named without turning off SELinux

## Fedora 28
* **NOTE:** Make sure in your hosts file to add your Fedora servers like so "xxx.xxx.xxx.xxx ansible_python_interpreter=/usr/bin/python3"
* Installs and configures Firewalld
* Installs and configures Named
* Configures SELinux to allow Named without turning off SELinux

## Ubuntu 18.04 LTS
* **NOTE:** Python must be installed on your server for this to work _sudo apt-get install python_
* Installs and configures Bind9
* Installs and sets UFW to allow SSH and Port 53 (doesn't do any other changes)

## To-Do
* Debian Support
* Ubuntu 20.04 LTS Support
