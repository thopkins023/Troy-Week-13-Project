# Troy-Week-13-Project
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

Where diagram can be found: Pictures/Saved Pictures/Troy_CSN.png)

The files that I have created were involved with producing a live ELK deployment on Microsoft Azure. They’re used to remake the entire deployment, or possibly focus on specific areas. 

-Playbook files used in the process: pentest.yml, elk.yml, filebeat-playbook.yml, metricbeat.yml

This document contains the following details:
- Topology
- Access Policies Listed
- ELK Configuration
  - Filebeat/Metricbeat
  - Machines Being Monitored
- How to Use the Ansible Build

### Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the applications will be heavily managed, and 
it will prevent data overload to the virtual machine addition to restricting excessive traffic to the network.


What aspect of security do load balancers protect? What is the advantage of a jump box?

Load balancers monitor and protect the system from frequent DDos attacks, and help balance traffic coming in. The jump box allows for users to receive access from a single node that is secured.

Integrating an ELK server allows users to easily monitor the vulnerable 
VMs for changes to the data and system load balancing.

What does Filebeat watch for? What does Metricbeat record?_

Filebeat watches for any information in the file system which has been changed and when it has. Metricbeat takes the metrics and statistics that collects and ships them to the output you specify

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.
| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| JumpBoxP | Gateway  | 10.0.0.10  | Linux            |
| ELKSERVER|ELK Server| 10.1.0.4   | Linux            |
| Web1     |Web Server| 10.0.0.13  | Linux            |
| Web2     |Web Server| 10.0.0.14  | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:

Add whitelisted IP addresses Public IP address from home

-Which machine did you allow to access your ELK VM? What was its IP address?

JumpBoxProvisioner 10.0.0.10

A summary of the access policies in place can be found in the table below.
| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box |    No               |10.0.0.1/10.0.0.2/67.4.207.227|
| ELKSERVER|    No               |                      |                                                           | Web1     |    No               |                      |
| Web2     |    NO               |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...

Advantage(s) of automating configuration with Ansible? The Advantage is that you can put commands into multiple servers from a single playbook.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
•  Install: docker.io 
•  Install: python-pip 
•  Install: docker 
•  Command: sysctl -w vm.max_map_count=262144 
•  Launch docker container: elk

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

 

Where image is found: C:\Users\thopk\OneDrive\Documents
### Target Machines & Beats
This ELK server is configured to monitor the following machines:

DVWA-VM1 10.0.0.5 DVWA-VM2 10.0.0.6

We have installed the following Beats on these machines:
Filebeat and metricbeat

These Beats allow us to collect the following information from each 
Machines:

Filebeat collects the changes done to data, and Metricbeat collects metrics and statistics.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the Ansible ELK installation and VM configurations 
- Run the playbook elk.yml and navigate to the ELK Server to check that the installation worked as expected.

Command: ansible-playbook /etc/ansible/pentest.yml
         ansible-playbook /etc/ansible/elk.yml
         ansible-playbook /etc/ansible/pentest.yml
         ansible-playbook /etc/ansible/ metricbeat.yml
         ansible-playbook /etc/ansible/ filebeat-playbook.yml




• Which file is the playbook? /etc/ansible/file/elk.yml 

• Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on? edit the /etc/ansible/host file to add webserver/elkserver ip addresses 

•  Which URL do you navigate to in order to check that the ELK server is running? www. 13.93.142.207:5601 (Kibana)
