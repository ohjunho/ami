# OpsFlex Toolchain IaC Project

This is the IaC project for OpsFlex Toolchain.


# Packer
Packer is a free and open source tool for creating golden images for multiple platforms from a single source configuration.
## Builder
AMI, Docker ..
## Provisioner
Shell, Ansible..
## Template
The configuration file used to define what image we want built and how is called a template in Packer terminology. 
The format of a template is simple JSON. 

# Ansible
Ansible is the simplest way to automate apps and IT infrastructure. 
Application Deployment + Configuration Management + Continuous Delivery.
The format of a template is simple yml. 
## Inventory
Target server list
## Playbook
What to do
## Task
How to do 

## Build infrastructure for OpsFlex
cmd $ cd ~
cmd $ mkdir workspace
cmd $ cd workspace

/* git clone */
cmd $ git clone https://github.com/opsflex/ami.git
cmd $ cd ~/workspace/iac/packer

/* perform packer command */
cmd $ packer build default.json