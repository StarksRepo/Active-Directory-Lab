# Active-Directory-Lab
## Objectives
* Install Windows Server 2019.
* Create a Windows Domain.
* Install and configure a domain controller using Active Directory.
* Create and organize objects such as users and security groups using Active Directory.
* Create and manage group policies (GPO) to perform the actions listed below:
  * Allow/Disallow access to certain applications.
  * Allow/Disallow access to certain folders.
  * Map set folders automatically.
  * Disable the download of executable files.
  * Set up day and time restrictions.
## Windows Server 2019 
1. Set Static IP Address
 * Using a static IP address is best for documentation and management (ex. firewall rules). Static IP addresses allows the server to have its own set IP address rather than depending on the DHCP server to provide us one. This will lessen the possibility of a server outage due to a failing DHCP server.
 * Server IP set to 172.16.0.1

<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/63e44321-a82d-4037-9e3e-48300c896441" width=300>

2. Installing Active Directory Domain Services (AD DS)
 * Rather than configuring each individual workstation and their users, we create a domain and centralize all settings on one server. The creation and management of domain users and computers on the
domain are managed by Active Directory (AD).
<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/f35e0f6e-fa7c-479d-9e45-4442207f9fcd" width=300>
<img width="300" alt="4-1024x604-1" src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/ef9fe9ec-b89a-4355-abee-c31d277f2d4e">
<img width="300" alt="5-1024x664-1" src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/6096a936-8fac-4229-b4f6-14cfeb3036ca">
<img width="300" alt="6-1" src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/8ec70490-c7da-4a30-a073-a94b793fdf9f">
<img width="300" alt="8" src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/72958ca4-befa-4c23-9bbb-07ec005bb284">

## Creating Admin User 
Now we are going to create an admin user account and add them to Domain Admins group in AD.
1. Open Active Directory Users and Computers.
2. Right click on your domain.
3. Click *new*, then click *user* and fill out the information as I did below to create your admin user. 
 <img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/626cae37-96e6-4765-ba1f-ab201fbb9c24" width=300>
 
4. Set the user password to something you can remember, hit *next* and then *finish*
5. After creating the user, right click on the users name and select *properties*, then *memeber of* and add the user to *Domain Admins*
  
<img src="https://github.com/StarksRepo/Active-Directory-Lab/assets/155681117/552c561d-baec-40b7-b09e-bacf1f3909bd" width=300>



## Adding Users to AD via Powershell
1. From the start menu navigate to PowerShell ISE and then open the script on the desktop named 1_CREATE_USERS inside of your PowerShell ISE instance
