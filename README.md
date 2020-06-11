# ELK-server
Network Diagramming and README
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](!ElkArchitecture.png(https://drive.google.com/file/d/18r1YjSIjRXjnp94W VPfMFaH_BSNCYmVp/view?usp=sharing)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._
playbook.yml(https://drive.google.com/drive/folders/1wCnzmhNNLTOx7FAY5 ovYpy-VP08CYG5U)
This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting traffic to the network.
- _TODO: What aspect of security do load balancers protect? Protects the availability
What is the advantage of a jump box? 
Jump Box serves as a gateway router and serves as a single node by securing and monitoring traffic called FANNING IN.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logfiles and system metrics.
- _TODO: What does Filebeat watch for? - Log files
- _TODO: What does Metricbeat record? - System Metrics

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| DVWA-VM1 | WebServer| 10.0.0.5   | Linux            |
| DVWA-VM2 | WebServer| 10.0.0.7   | Linux            |
| ELK      | Elkserver| 10.0.0.6   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the LoadBalancer machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_
  
Machines within the network can only be accessed by Jump Box.
- _TODO: Which machine did you allow to access your ELK VM? - Jump Box
What was its IP address? - 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | Host Machine         |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_
We can rerun the configuration as many times as needed.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Increase Virtual Memory
- Install Docker
- Install Pip 
- Use Pip Module
- Download and Launch Elk Container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)
!docker_ps_output.png(https://drive.google.com/drive/folders/1L3D6Xn4O 7gEtS3_iyxa9dVkVLTgmSPx0?usp=sharing)
### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_
- DVWA-VM1 - 10.0.10.5
We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_
- filebeats
These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
- Filebeat was collecting the system logs from DVWA-VM1 machine.
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the /files/filebeat-configuration.yml file to filebeat.yml.
- Update the /etc/ansible/hosts file to include... - ports
- Run the playbook, and navigate to <ElkserverIP>:5601 to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? - filebeat-playbook.yml
- _Where do you copy it? - /roles/filebeat.yml
- _Which file do you update to make Ansible run the playbook on a specific machine? - /etc/ansible/hosts
- _How do I specify which machine to install the ELK server on versus which to install Filebeat on? hosts: elkserver
- _Which URL do you navigate to in order to check that the ELK server is running? - <ElkserverIP>:5601

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
