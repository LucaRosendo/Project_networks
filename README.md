# Project_2
Repository created for the implementation of the second bimester project in computer networks.


<div class="Componentes">

## Group 3: 
> Member 1: Jessé Diego;</br>
> Member 2: Maria Beatriz;</br>
> Member 3: Maria Roberta;</br>
> Member 4: Lucas Rosendo.
<div/>

## Objective:

The objective of this project is to reconcile 8 VM's from different computers and demonstrate step by step of their creation as well as their operation.

## Step by step:

   1. Create a network environment, which must contain 8 virtual machines with OS. Ubuntu Server.
   2. Create a tutorial/roadmap document containing the step-by-step configuration and execution of a virtualized network environment.
   3. List the hardware configuration used in each VM. (Ex.: amount of memory, number of processors/cores, disk space.
   4. IP addressing and group name will be identified by the group name-number pair (example Group1), remembering that the first IP is the network IP, and the last is the broadcast IP.
       - Create a table with the definitions of the IPs of the VMs with the netmask /28 (255.255.255.240).
       - Class 914 will use the 192.168.14.0/24 network to create group subnets.
       - Class 924 will use the 192.168.24.0/24 network to create group subnets.
       - Class 913 will use the 192.168.13.0/24 network to create group subnets.
       - Class 923 will use the 192.168.23.0/24 network to create group subnets.
       - Examples:
          * Group 1 of class 914 will use lane 192.168.14.[0-15]/28
          * Group 4 of class 924 will use lane 192.168.24.[48-63]/28
          * Group 2 of class 913 will use lane 192.168.13.[16-31]/28
          * Group 6 of class 923 will use lane 192.168.23.[80-95]/28
          
   5. Create a table with name definitions for hostname, domain names (FQDN), aliases (aliases) and IP addresses of the VMs.
       - The domain must obey the format: ```<grupoX-9yz>.ifalara.net```
       - Example for the hostname of the VMs:
            * frances.grupo2-913.ifalara.net
            * pajucara.grupo5-914.ifalara.net
            * vm02-pc3.grupo2-923.ifalara.net

   6. Edit hostnames in S.O. of each VM and add the IP/Names mapping in the /etc/hosts file of each VM.
   7. In each vm must have the administrator user and the users with the names of the members of the group.
   8. Need to create new VMs for the Project.
   9. Put in the tutorial the results of all ping tests and SSH access using the users created in the VMs and the hostnames.

