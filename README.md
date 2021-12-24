# Project-1
Project 1 for Cybersecurity class, ELK server and VMs
## Overview
This will cover Project-1 of the UofM Cybersecurity class
The overall conclusion should be (at least) two web servers, a jumpbox provisioner, a ELK server, and a Load balancer to manage it all.

## Overall Conclusion table
|Name|Function|Internal IP Address|External IP|OS|
|----|--------|-------------------|-----------|--|
|Jumpbox provisioner|Gateway|10.0.0.4||Linux|
|Web-1|DVWA|10.0.0.7|External IP|Linux|
|Web-2|DVWA|10.0.0.8|External IP|Linux|
|ELK|Log Server|10.2.0.4|External IP|Linux|

|Name|Is it Publicly Accesible|Allowed IP Addresses|
|----|------------------------|--------------------|
|Jumpbox|Yes|My Personal IP|
|Web-1|No|Load Balancer 40.122.130.60 and Jumpbox 40.122.152.135|
|Web-2|No|Load Balancer 40.122.130.60 and Jumpbox 40.122.152.135|
|ELK|Yes|My Personal IP|
