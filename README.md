# Active-Directory-Lab
## Objectives
* Install VirtualBox. (https://www.virtualbox.org/wiki/Downloads)
* Install Windows Server 2019. (https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019)
* Create a Windows Domain.
* Install and configure a domain controller using Active Directory.
* Create and organize objects such as users and security groups using Active Directory.
* Create and manage group policies (GPO) to perform the actions listed below:
  * Allow/Disallow access to certain applications.
  * Allow/Disallow access to certain folders.
  * Disable the download of executable files.


## Virtual Machine Configuration
1. Click on *Tools* from the VirtualBox sidebar and select *New*.

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/9b9da838-bf03-4fa4-a335-924c933ba76b" width=500>

2. Give the VM a name. Ensure that the Folder option points to the location where all the Home Lab-related VMs are saved. For the ISO Image select the downloaded Windows Server 2019 image. Select the *Skip Unattended* Installation option and then click on *Next*.

3. Increase the Memory to 4096MB (4GB) and click on *Next*.

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/427e3887-ebc6-423d-9083-f8bee0a05d8f" width=500>

4. Increase the Hard Drive size to 100GB and then click on *Next*.

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/e1857489-4518-4e26-9ff5-ddd2c5aa6946" width=500>

5. Confirm that all the values look correct and then click on *Finish*.

## Network Configuration
From the taskbar right-click on the network icon and select Open Network & Internet settings.


Click on “Change adapter options”.

On the Network Connections page, we should see the Ethernet adapter. Right-click on the adapter and select Properties.

Select Internet Protocol Version 4 (TCP/IPv4) and click on Properties.

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/b62c511c-0c92-4018-b2c5-2a46991b40d5" width=500>

Enter the details as shown below and then click on OK. Click on OK again to close the Ethernet Properties menu.

IP address: 172.16.0.1

Subnet mask: 255.255.255.0

Preferred DNS Server: 127.0.0.1

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/114dceb2-96aa-4e98-bc54-07e0a3b9e5a5)" width=500>

## Active Directory & DNS Installation

1. Open Server Manager.
2. Navigate to "Add Roles and Feautres."
3. Proceed with the on-screen instructions by selecting "Next" and "Next" again.
4. Choose your server for the installation.
5. Select "Active Directory Domain Services" as the Role.
6. Continue with "Next," "Next," and "Next."
7. Finally, Click on "Install" to initate the installion process.
Following these steps, you'll seamlessly integrate Active Directory Domain Services into the server configuration.

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/9e3aa44d-270d-4da6-83cb-3352d4e77bd7)" width=500>

Continuing the setup, we will select "Add a new forest" and follow the steps below:

1. In the wizard, choose "Add a new forest."
2. Specify a generic root domain name; for instance, use "mydomain.com."
3. Proceed to the next step by clicking "Next."

This configuration will set up a new forest with the specified root domain name. Following these instructions will help establish the foundation for your Active Directory environment.

After a restart, I accessed the newly created Active Directory to set up a new Organizational Unit (OU), which we named "_ADMINS." Following the creation of this OU, a new user was added under this specific OU. This step ensures a well-organized structure within Active Directory, making user management more efficient and structured.

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/f2958a8c-2c18-4e21-81dc-62accaac82b8)" width=500>

You will add your user to the admin group. Click on "Admin," then go to "New" and select "User." Enter the desired username and password. 

After setting up the user account, log out of the current user and attempt to log in with the newly created credentials.

Now that the first Domain Admin user is established, log out and log into the server using this new user account. This user will have administrative privileges within the Active Directory domain.

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/81e10c03-5557-438c-86b5-994b289eaedc)" width=500>

The next crucial step is to promote the Active Directory (AD) to a Domain Controller. This action transforms the server into a central hub that all client computers will access to connect to the internet. This promotion establishes a hierarchical and organized structure within the network, ensuring efficient communication and access for all connected devices.

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/a23a482d-8d8a-42cb-9bbd-b962b5816ece)" width=500>

## Second Part of RAS / NAT / DHCP

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/94f3f2d9-bd03-4714-a88f-2fbb210329b0)" width=500>

Following that, the next step involves setting up the Remote Access Server (RAS) and Network Address Translator (NAT). 
This configuration empowers the client computer, once it's configured, to access the internet through the Domain Controller. By implementing RAS and NAT, you establish a seamless connection for client devices to utilize the internet resources while maintaining a secure and centralized network environment through the Domain Controller.

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/d9f34745-93cd-4e53-b2c8-f2fc1654e17c)" width=500>

To set up the Remote Access Server (RAS) and Network Address Translator (NAT), follow these steps:
1. Open "Add Roles & Features" and proceed by selecting "Next."
2. In the "Roles" section, check "Remote Access" and continue with "Next."
3. On the "Select Role Services" page, check "Routing," and additional features, such as "Remote Access Service (RAS)," will automatically be selected. Click "Next" to proceed.
4. Follow the prompts until the installation is complete and then close the wizard.

Now, access the tools by going to "Routing and Remote Access":
1. Right-click on the Domain Controller.
2. Choose "Configure and Enable Routing and Remote Access."
3. In the configuration wizard, select NAT (Network Address Translator).
4. If no network interfaces show up, close the window and open it again.
5. Choose the "INTERNET" interface and complete the configuration.
By following these steps, you enable remote access and NAT, allowing client computers to access the internet through the Domain Controller.

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/fdfb67c5-b568-4bc5-97aa-fa29c990ca2f)" width=500>

## DHCP Configuration

Proceed to configure DHCP (Dynamic Host Configuration Protocol) by following these steps:
1. Click on "dc.mydomain" and check "IPv4."
2. In the DHCP management console, create an IP address scope for the users.
3. Set the DHCP IP address scope to 172.16.0.100-200. This range will allow for the assignment of new IP addresses to devices within your network.
By establishing this DHCP IP address scope, you ensure that devices connecting to your network will be dynamically assigned IP addresses within the specified range, facilitating efficient and automated network configuration.

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/bd7bbad8-eedd-4d56-958b-40d7a82c5ba3)" width=500>






