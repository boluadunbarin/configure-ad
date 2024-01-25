<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- 1) Setup resources in azure
- 2) Ensure connectivity between client and domain controllers
- 3) Install active directory
- 4) Create Admin and Normal User account
- 5) Join client to domain
- 6) Setup remote desktop for normal users
- 7) Create many other users

<h2>Deployment and Configuration Steps</h2>

![23](https://github.com/boluadunbarin/configure-ad/assets/157642328/7fd8bc9c-ac8f-435b-b3be-853d5eb6f821)

Create virtual machine (windows server 2022) named dc1

![24](https://github.com/boluadunbarin/configure-ad/assets/157642328/38b04302-f7bd-4496-b042-b771d3f655f1)

Set Domain Controller’s NIC Private IP address to be static

![25](https://github.com/boluadunbarin/configure-ad/assets/157642328/ae97c4b8-ef99-4db6-924a-f8cb10204953)

Create client1 virtual machine with windows 10 with same vnet as dc1

Log into client1 using remote desktop connnection

![26](https://github.com/boluadunbarin/configure-ad/assets/157642328/e6ef85b9-18ac-46a3-9dab-24d2da97de92)

Ping dc1 private ip address

![27](https://github.com/boluadunbarin/configure-ad/assets/157642328/40566b17-19e9-491e-86a6-8414f6db0c82)

![28](https://github.com/boluadunbarin/configure-ad/assets/157642328/9ed30296-de24-4365-b3dd-3867996ebbc0)

Log into dc1 and enable ICMPv4 on the firewall

![29](https://github.com/boluadunbarin/configure-ad/assets/157642328/953ecd2a-4a4f-4a25-83ac-d1ff56c983b5)

Check connectivity

![31](https://github.com/boluadunbarin/configure-ad/assets/157642328/5bde578e-22f2-4522-8280-bd14a776cde9)

![33](https://github.com/boluadunbarin/configure-ad/assets/157642328/18e9e0e9-5d6e-426f-b080-e69a2b29b385)

Install active directory domain  in dc1

![34](https://github.com/boluadunbarin/configure-ad/assets/157642328/b7abaa64-c565-42fa-bdee-84fc7bc6d8fc)

Click the exclamation mark icon promote as a domain controller to set up a new forest called mydomain.com

Restart and then log back into DC-1 as user: mydomain.com\gftbnd

![35](https://github.com/boluadunbarin/configure-ad/assets/157642328/7a8f5cb5-1797-425e-abc7-c1f54674994a)

Open ADUC

![36](https://github.com/boluadunbarin/configure-ad/assets/157642328/c4db4ded-4e47-42ef-8203-5d490a359cd5)

![37](https://github.com/boluadunbarin/configure-ad/assets/157642328/8b15f90a-08a5-4c4d-9706-9b8ad71179fc)

Create _EMPLOYEES and _ADMINS OU folder

![38](https://github.com/boluadunbarin/configure-ad/assets/157642328/8b4fad17-0365-42a2-bc1e-23d81f9fdc3b)

Create employee Jane Doe

![39](https://github.com/boluadunbarin/configure-ad/assets/157642328/b6acbe1d-e99e-44de-921b-49392af6e1c7)

Add her to the domain admins security group
Log out and log back in as mydomain.com\jane_admin

![40](https://github.com/boluadunbarin/configure-ad/assets/157642328/a59f8bcf-81f8-40dd-afe4-257b6b2f508b)

From the Azure Portal, set Client-1’s DNS settings to the DC’s Private IP address

Restart client1 from azure portal

![41](https://github.com/boluadunbarin/configure-ad/assets/157642328/ec9509b7-b7d1-42aa-87fd-3823a84c5c55)

Login to client1 (Remote Desktop) as the original local admin (gftbnd) and join it to the domain (computer will restart)

Login to the Domain Controller (Remote Desktop) and verify client1 shows up in Active Directory Users and Computers (ADUC) inside the “Computers” container on the root of the domain
Create a new OU named “_CLIENTS” and drag client1 into there

Setup Remote Desktop for non-administrative users on Client-1
Log into Client-1 as mydomain.com\jane_admin and open system properties
Click “Remote Desktop”

![42](https://github.com/boluadunbarin/configure-ad/assets/157642328/69302de7-b06a-4a2e-a731-de919735cb9f)

![42_adun](https://github.com/boluadunbarin/configure-ad/assets/157642328/91b46159-b4d7-4cb5-8e26-4673dbd3ac5d)

Allow “domain users” access to remote desktop
You can now log into client1 as a normal, non-administrative user now

Login to DC-1 as jane_admin

![44](https://github.com/boluadunbarin/configure-ad/assets/157642328/152cf2c8-2f1b-436c-9776-1aff4b92431e)

Open powershell as an administrator

Create a new File and paste the contents of the script into it (https://github.com/joshmadakor1/AD_PS/blob/master/Generate-Names-Create-Users.ps1)
Run the script and observe the accounts being created
When finished, open ADUC and observe the accounts in the appropriate OU
attempt to log into Client-1 with one of the accounts 


