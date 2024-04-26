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

## Windows Server 2019 Setup
1. Select Windows Server 2019 from the sidebar and click on *start* from the toolbar.

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/b092ff8a-b8f3-430f-8513-a2bc010e037a" width=500>

2. Click *Next*0.
3. Click *Install now*
4. Select *Windows Server 2019 Standalone Evaluation (Desktop Experience)* and click on *Next*.

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/27e7f054-53bc-4a9b-8a11-905458e4e9d9" width=500>

5. Accept the agreement and click on *Next*.
6. Select Custom: Install Windows only (Advanced).
7. Select Disk 0 and click on Next.

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/d97f7cc4-110c-448a-b0d8-41c2749fe54a" width=500>

The VM will restart a couple of times during this installation process.
## OS Setup & Configuration
Once the installation is complete we will be asked to set the password for the Administrator account. Once set click on Finish.

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/62ed7e5e-149b-4afc-b063-5f0265bc3134" width=500>

Once you log in. Server Manager will automatically open. A popup will also open asking us to try Windows Admin Center. Click on Don't show this message again and then click on X to close the popup.

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/70487ae1-2b5e-48a1-bb0c-370b1ec8e6ae" width=500>

## Network Configuration
From the taskbar right-click on the network icon and select Open Network & Internet settings.

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/13fbd220-dacc-463d-9f94-5610789329b5" width=500>

Click on “Change adapter options”.

On the Network Connections page, we should see the Ethernet adapter. Right-click on the adapter and select Properties.

Select Internet Protocol Version 4 (TCP/IPv4) and click on Properties.

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/b62c511c-0c92-4018-b2c5-2a46991b40d5" width=500>

Enter the details as shown below and then click on OK. Click on OK again to close the Ethernet Properties menu.

IP address: 10.80.80.2

Subnet mask: 255.255.255.0

Default gateway: 10.80.80.1

Preferred DNS Server: 10.80.80.2

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/20dfa633-cc4a-4cd6-86f2-45425df9debe" width=500>

## Active Directory & DNS Installation












