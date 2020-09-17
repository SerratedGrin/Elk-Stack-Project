# Elk-Stack-Project
# Jon Maguire's Elk Stack Project

## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

<img src="https://github.com/SerratedGrin/Elk-Stack-Project/blob/master/ELK%20Diagram.jpg" />

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above, or select portions of the provided files may be used to install specific pieces of the deployment - such as [Filebeat](https://github.com/SerratedGrin/Elk-Stack-Project/blob/master/filebeat-config.yml).


This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, scalable, and reliable - in addition to restricting unsecured access to the network.

First and foremost - the load balancer's off-loading function, or distribution of traffic across multiple servers, mitigates Denial of Service attacks. This highly valuable security measure alone highlights the benefit of a load balancer.

Load balancers also offer a health probe function, obtaining reports of servers with issues and stops sending traffic to said servers. 

Note that Filebeat is a separate entity within the diagram, but it is a running service on the DVWA host machines - gathering log data to export to the ELK application (specifically, to ElasticSearch and/or Logstash).

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _TODO: What does Filebeat watch for?_
- _TODO: What does Metricbeat record?_

The configuration details of each machine may be found below.

| Name                 | Function          | IP Address     | Operating System |
|----------------------|-------------------|----------------|------------------|
| Jump-Box-Provisioner | Gateway           | 52.191.162.187 | Linux            |
| DVWA-LD              | Load balancer     | 40.125.123.181 | N/A              |
| Red-Team-Web-VM-1    | DVWA host machine | 10.10.0.9      | Linux            |
| Red-Team-Web-VM-2    | DVWA host machine | 10.10.0.10     | Linux            |
| Red-Team-Web-VM-3    | DVWA host machine | 10.10.0.11     | Linux            |
| ELK-Server           | ELK host machine  | 52.252.58.97   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump-Box_Provisioner machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_

Machines within the network can only be accessed via SSH port 22 through the Docker container loaded on the Ansible machine.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because the process eliminates potential human error and makes the process significantly more efficient - particularly while utilizing a bash script to establish multiple configurations with one command. There are, however, specific elements that will need to be modified to accurately configure according to the parameters of the topology (virtual networks and their respective IP addresses and/or subnets, as was modified in this particular case for the filebeat-config.yml).

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
