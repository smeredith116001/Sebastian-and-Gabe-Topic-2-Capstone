MAAS Installation Documentation 
Below is a link that takes you through the process of how to install MAAS, this document is also going to go through Gabe and I’s the installation of the product 
 https://www.youtube.com/watch?v=WF9eRpFS0VQ&ab_channel=IbrahimMarey

Here are the commands related to the installation of MAAS on a ubuntu system
First, you start by following these commands
###### Install Mass
`sudo snap install maas`  

###### Install Database
`sudo snap install maas-test-db`     

###### Start Database
`sudo snap start maas-test-db`

###### Configure Controller and URI
`sudo maas init region+rack --database-uri maas-test-db:///`

###### Check Config
`sudo maas config`

###### Check Status
`sudo maas status`

######


Afterward, you need to navigate to the IP of the machine that the product is running on and like many other products it will bring you to this web page with a UI showing that MAAS was installed 
<img width="774" alt="Screenshot_20221109_032804" src="https://user-images.githubusercontent.com/78443183/202925069-271226ca-4db6-482e-aae8-4284f283ce46.png">   

Below is the page that you are able to choose which images will be available for deployment:
<img width="729" alt="Screenshot_20221109_032712" src="https://user-images.githubusercontent.com/78443183/202925093-74602636-cc58-459a-977d-01d889559819.png">  

Next, upload your public SSH key in order to access the web UI and machines
<img width="745" alt="Screenshot_20221109_033328" src="https://user-images.githubusercontent.com/78443183/202925220-8dabdbce-f0a3-41ad-b6c1-cf116492d6dc.png">


After the program has been successfully installed we begin the process of the main function of this program which is to have other boxes be managed and deployed via this program. We will bring you through the installation and setup process, There will be a troubleshooting section as well that will provide you with steps if there are any issues along the way. I also recommend that you refer to the video we displayed at the beginning for any of the steps before this if there are any issues with getting to this point. 

From this point, you should be able to see a page where the boxes can be managed. The section initially will be empty so we will bring you through how to get a box up and running using MAAS 

PXE boot is something that is required in order to boot a server with MAAS
Here is a link that brings you through what steps you need to take in order to enable PXE Boot
https://www.intel.com/content/www/us/en/support/articles/000054990/intel-nuc/intel-nuc-kits.html
If you have trouble finding this setting refers to the issues page at the bottom of this document 

Once you boot up the server, you need to enter BIOS as you did for the PXE boot setting, Then you need to go to Boot order and select to boot over the network, After that MAAS takes it past this and should begin booting up the selected device 

Afterward, you can see the device inside of MAAS similar to the screenshot below
<img width="712" alt="Screenshot_20221110_070351" src="https://user-images.githubusercontent.com/78443183/202925674-f6d9bb6e-3b8b-476a-b2c4-d93a0763b7aa.png">


There is multiple options you can choose once you select the box that will give you information about it and what it is doing
<img width="337" alt="Screenshot_20221110_072105" src="https://user-images.githubusercontent.com/78443183/202925680-396df5e9-382e-4bbe-9afd-86ce7ea8f570.png">

Summary: Is the main page where you can see the specs of the devices, This is similar to what you would expect to be a Dashboard showing the network connections it is making as well as a general overview of the device 

Network: Shows the different apdaters connected

Storage: Allows you to see the storage on the device as well as any partitions made 
PCI devices 

USB: is all settings related to the USB inputs on the device

Commissiong: Shows what commissions have been cleared as well as it gives the option to make some changes as we did here
<img width="545" alt="Screenshot_20221110_072611" src="https://user-images.githubusercontent.com/78443183/202925690-9e14f1d3-7ee0-4111-8065-3f83044326c9.png">    

Our Commisson changes     
<img width="664" alt="Screenshot_20221110_072022" src="https://user-images.githubusercontent.com/78443183/202925697-aeaa6f06-f93d-4478-ae5f-7735429bde9e.png">

Tests: Allows you to run certain tests that you may need to check certain parameters are working based on what this box will be used for 
Logs: Similar to a program like Wazuh it shows all the logs of the actions running on the server as well as any changes made to settings involving the box

Configuration: Allows you to access settings for Configuration that involve mostly the machine configuration and power configuration 

After all the settings are set and you are sure that everything is in order for what the server will be doing you can boot into the device(Note: Certain logins require a SSH key from Ubuntu in order to access 
Issues: MAAS as a program requires physical boxes to use PXE boot which depending on the Servers specs and level of OS it may not be an option for every server as it is a fairly newer type of setting 
