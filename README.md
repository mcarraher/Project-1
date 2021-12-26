# Project-1
Project 1 for Cybersecurity class, ELK server and VMs

The files in this repository were used to configure the network depicted below.

<img width="871" alt="My azure environment" src="https://user-images.githubusercontent.com/89100722/147370335-5b4ac558-08d7-4b35-b16c-3fda4b4af0e1.PNG">


These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the YAML file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly secure, in addition to restricting access to the network.
The load balancer make susre that is one server is down/at full capacity then it will automatically switch to the other server. The Jumpbox acts as a gateway for the entire VNet.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the network and system files.
-Filebeat collects Logging data from specific files or locations
-Metricbeat records Metric data from servers and services

The configuration details of each machine may be found below.

|Name|Function|Internal IP Address|External IP|OS|
|----|--------|-------------------|-----------|--|
|Jumpbox provisioner|Gateway|10.0.0.4|40.122.152.135|Linux|
|Web-1|DVWA|10.0.0.7|40.122.130.60|Linux|
|Web-2|DVWA|10.0.0.8|40.122.130.60|Linux|
|ELK|Log Server|10.2.0.4|20.120.28.62|Linux|

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: My Personal IP Address

Machines within the network can only be accessed by an asymmetric key from the jumpbox.

A summary of the access policies in place can be found in the table below.

|Name|Is it Publicly Accesible|Allowed IP Addresses|
|----|------------------------|--------------------|
|Jumpbox|Yes|My Personal IP|
|Web-1|No|Load Balancer 40.122.130.60 and Jumpbox 40.122.152.135|
|Web-2|No|Load Balancer 40.122.130.60 and Jumpbox 40.122.152.135|
|ELK|Yes|My Personal IP|

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
Everything will be set up properly and easily, no chance of missing anything during install.

The playbook implements the following tasks:
- Install docker, Pip3, and Python Docker modules
- Increase VM Memory
- installs and opens containers for the ELK server

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

<img width="1517" alt="ELK NEW" src="https://user-images.githubusercontent.com/89100722/147414245-b06de998-3f52-4d7b-83a7-5d9451bb55e1.PNG">

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
Web-1 10.0.0.7
Web-2 10.0.0.8

We have installed the following Beats on these machines:

Installed metricbeat and filebeat

These Beats allow us to collect the following information from each machine:
These beats allow us to see metrics on location worldwide on who is accessing our servers, as well as activity actively on the server.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the YAML file to your terminal.
- Update the YAML file to include the IP address of your ELK machine
- Run the playbook, and navigate to Kibana to check that the installation worked as expected.

Which file is the playbook? Where do you copy it? 

/etc/ansible/

Which file do you update to make Ansible run the playbook on a specific machine? 

/etc/ansible/hosts.cfg

Which URL do you navigate to in order to check that the ELK server is running? 

http://[your.VM.IP]:5601/app/kibana
