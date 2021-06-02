# Homework
Homework #13
AUTOMATED ELK STACK DEPLOYMENT<img width="381" alt="ELK" src="https://user-images.githubusercontent.com/84407865/120537752-834a5a00-c39a-11eb-932a-15eb6fdb81e9.png">


These files have been tested and used to generate a live ELK
deployment in Cloud.



Details:

-Description of the Topologu<img width="381" alt="ELK" src="https://user-images.githubusercontent.com/84407865/120537875-a8d76380-c39a-11eb-9b94-c9c65160abbc.png">


-Access Policies

-ELK Configuration

-Beats in Use

-Machines Being Monitored

-How to Use the Ansible Build


Description of the Topology

The main purpose of this network is to expose a load-balanced and
monitored instance of DVWA.

Load balancing ensures that the application will be highly available,
in addition to restricting inbound access to the network.

-Load balancing is the process of distributing network traffic across
multiple servers. This ensures no single server bears too much demand.
By spreading the work evenly, load balancing improves application
responsiveness. In a security aspect, load balancers can defend an
organization against denial-of-service (DDos) attacks.
-Jump box's provide an additional layer of security from the public
internet by controlling access to the other machines by allowing
connections from specific IP addresses and forwarding to those
machines.

-Integrating an ELK server allows users to easily monitor the
vulnerable VMs for changes to the file systems of the VM's on the
network and system metrics.

-Filebeat collects data about the file system.

-Metricbeat collects machine metrics, such as uptime.



Access Policies

The machines on the internal network are not exposed to the public Internet.

-Only the jump box machine can accept connections from the Internet.
Machines within the network can only be accessed by the Jump Box.

-Only the Jump Box has access to the ELK VM




Elk Configuration


Ansible was used to automate configuration of the ELK machine. No
configuration was performed manually, which is advantageous because it
allows for consistent, repeatable configuration that reduces the time
of deployment and errors.

The playbook implements the following tasks:

-Install Docker

-Install Python3-pip

-Install Docker python module

-Download and launch ELK container

-Enable service Docker on boot

Target Machines & Beats

We have installed the following Beats on these machines:

-Filebeat

-Metricbeat

These Beats allow us to collect the following information from each machine:

-Filebeat collects linux logs. This allows us to track things like
user logon events, failed access attempts, service starts and stops.

-Metricbeat collects system metrics from the web servers. We look for
things like cpu usage, memory usage, drive space usage and drive space
available for each host.


Using the Playbook

In order to use the playbook, you will need to have an Ansible control
node already configured. Assuming you have such a control node
provisioned:

SSH into the control node and follow the steps below:

-Copy the ansible.cfg file to ~/etc/ansible.

-Update the hosts file to include the hosts that you would like to
manage, eg: [ELK]  ansible_python_interpreter=/usr/bin/python3

-Run the playbook, and navigate to http://[ELK.VM.IP]:5601/app/kibana
to check that the installation worked as expected.



