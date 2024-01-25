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

create domain controller (windows server 2022) named dc1

![24](https://github.com/boluadunbarin/configure-ad/assets/157642328/38b04302-f7bd-4496-b042-b771d3f655f1)

Set Domain Controller’s NIC Private IP address to be static

![25](https://github.com/boluadunbarin/configure-ad/assets/157642328/ae97c4b8-ef99-4db6-924a-f8cb10204953)

create client1 virtual machine with windows 10 with same vnet as dc1

log into client1 using remote desktop connnection

![26](https://github.com/boluadunbarin/configure-ad/assets/157642328/e6ef85b9-18ac-46a3-9dab-24d2da97de92)

ping dc1 private ip address

![27](https://github.com/boluadunbarin/configure-ad/assets/157642328/40566b17-19e9-491e-86a6-8414f6db0c82)

![28](https://github.com/boluadunbarin/configure-ad/assets/157642328/9ed30296-de24-4365-b3dd-3867996ebbc0)

log into dc1 and enable ICMPv4 on the firewall

![29](https://github.com/boluadunbarin/configure-ad/assets/157642328/953ecd2a-4a4f-4a25-83ac-d1ff56c983b5)

check connectivity

![31](https://github.com/boluadunbarin/configure-ad/assets/157642328/5bde578e-22f2-4522-8280-bd14a776cde9)

install active directory domain  in dc1
