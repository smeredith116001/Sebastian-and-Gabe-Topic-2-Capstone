### MAAS Overview
-------
Metal As A Service (MAAS) is an application thats main feature allows a user to provision a bare metal system with any OS remotly. This can either be a physical or virtual machine and can be provisioned in only a few steps. MAAS also has many system administration features as well as being able to be integrated with many different automation tools like Ansible and Juju. 

### MAAS life cycle
-------
###### New
In this step, the machine will be PXE booted and MAAS will enlist this machine

###### Commissioning
MAAS will take a full inventory of the machine. This includes items like storage, ram, cpu, connected devices, pcie devices, network information, and anything else regarding computer hardware. 

###### Ready
When a machine is ready, it means that is has successfully commissioned 

###### Allocated
This is when a machine is ready and is allocted to a specific user, who can configure the machine to their needs

###### Deploying
This stage is the actual deployment of the OS onto the machine. This is also the stage where any post deployment configuration happens. 

###### Releasing 
Once the machine is not needed anymore, it can be released meaning a full disk wipe happens and it is ready to be commisioned from scratch again. 

### MAAS Use Cases
------
* Small company that can take advantage of easy virtual machine deployment
* Large organizations that can take advantage of touchless deployment and automation
* Using MAAS in combination with ansible, juju, etc… to automate all steps of deployment and system configuration

### Troubleshooting Experiences 
If you are having trouble getting MAAS to work using the manual power option, it is very important to turn on the machine at the right time. First, turn on the machine and this will allow MAAS to enter the enlisting phase. After the machine is enlisted it will turn off. On the MAAS web interface the machine will be labeled as “new”. Next, on the web interface select “commission” and then turn the machine on again. After the commissioning phase is complete, the machine will turn off again. On the web interface select “deploy” and turn the machine on one last time. Now the machine will be deployed. It is very important to follow these power steps as turning the machine on at the wrong time may cause problems. 


