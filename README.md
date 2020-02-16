# SysDogs #2

Deploy k8s cluster with via Vagrant Virtualbox and Ansible based on Centos 7 image from vagrant repository

### Prerequisites

What things you need to install the software and how to install them


 - [ANSIBLE](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
 - [VAGRANT](https://www.vagrantup.com/downloads.html)
 - [VIRTUALBOX](https://www.virtualbox.org/wiki/Downloads)


### Usage
1. Clone this repository to your local drive
2. Go to place where you cloned this 
3. Run command : `vagrant up`  to start automation


### Removing

1. Go to place where you cloned this 
2. Run command : `vagrant destroy`  to remove everything what was created by vagrant 


## Tested on Kali Linux 2020.1

## INFO: By default it would create only 1 node if you want more you can manipulate `NODE_NUMBER` variable at the beginning of Vagrantfile.