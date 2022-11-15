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

### MAAS Use Cases
------
* Small company that can take advantage of easy virtual machine deployment
* Large organizations that can take advantage of touchless deployment and automation
* Using MAAS in combination with ansible, juju, etc… to automate all steps of deployment and system configuration

