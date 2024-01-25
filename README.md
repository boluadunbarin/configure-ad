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

![Screenshot 2024-01-24 184843](https://github.com/boluadunbarin/configure-ad/assets/157642328/b0c2390d-029b-4e8f-b232-bd79450f2013)

![Screenshot 2024-01-24 185048](https://github.com/boluadunbarin/configure-ad/assets/157642328/f42dc71a-4893-4538-badf-8c954247ba0c)

![Screenshot 2024-01-24 185152](https://github.com/boluadunbarin/configure-ad/assets/157642328/1200bf55-47bc-4f13-922e-bb0a778c3bed)

![Screenshot 2024-01-24 185538](https://github.com/boluadunbarin/configure-ad/assets/157642328/87546125-9402-4b35-881e-70fb97bd28b2)

![Screenshot 2024-01-24 185651](https://github.com/boluadunbarin/configure-ad/assets/157642328/db33010f-4b16-41d5-b97f-b1e4cb67a5f9)

![Screenshot 2024-01-24 185755](https://github.com/boluadunbarin/configure-ad/assets/157642328/32115bcf-3299-4c3a-a347-ba7df21098fe)

![Screenshot 2024-01-24 190532](https://github.com/boluadunbarin/configure-ad/assets/157642328/4dcb9f32-ab49-428b-a928-c1fd5b8c38bb)

![Screenshot 2024-01-24 191151](https://github.com/boluadunbarin/configure-ad/assets/157642328/17f9d648-ef45-4b7a-ae31-caa8b073a6a7)

![Screenshot 2024-01-24 191433](https://github.com/boluadunbarin/configure-ad/assets/157642328/c5d860fe-ff84-42b8-9442-789861afd7d5)

![Screenshot 2024-01-24 191733](https://github.com/boluadunbarin/configure-ad/assets/157642328/a713cdc9-1d66-4b3f-9347-d84fa6b981da)

![Screenshot 2024-01-24 191938](https://github.com/boluadunbarin/configure-ad/assets/157642328/4b326826-111f-42f8-be0d-2584d90a6edb)

![Screenshot 2024-01-24 192234](https://github.com/boluadunbarin/configure-ad/assets/157642328/e4f754e6-44ae-48c1-b788-17869ebced44)

![Screenshot 2024-01-24 192146](https://github.com/boluadunbarin/configure-ad/assets/157642328/2677abf8-3fc3-47ea-ae3f-a5309c0096ee)

![Screenshot 2024-01-24 192431](https://github.com/boluadunbarin/configure-ad/assets/157642328/03513143-a144-4d07-b834-5e83921741a4)

![Screenshot 2024-01-24 192751](https://github.com/boluadunbarin/configure-ad/assets/157642328/95877d2d-26db-4a3a-a2d9-f31c9bd416a7)

![Screenshot 2024-01-24 192952](https://github.com/boluadunbarin/configure-ad/assets/157642328/95fc60a3-0482-4a4c-86c5-e86e37387012)

![Screenshot 2024-01-24 193234](https://github.com/boluadunbarin/configure-ad/assets/157642328/8dac757f-a77c-452c-941d-ece3cc9b6a9a)

![Screenshot 2024-01-24 193501](https://github.com/boluadunbarin/configure-ad/assets/157642328/454bffa8-a72f-4317-9f7d-c0343bb49e2f)

![Screenshot 2024-01-24 194122](https://github.com/boluadunbarin/configure-ad/assets/157642328/331b3f4a-24f1-493a-a676-7d86e23d54a9)

![Screenshot 2024-01-24 194714](https://github.com/boluadunbarin/configure-ad/assets/157642328/1ade3f17-eda5-450b-a351-b6c87e3f7c10)

![Screenshot 2024-01-24 194914](https://github.com/boluadunbarin/configure-ad/assets/157642328/c7efdc68-e78f-4516-8a46-ac99f0aca1a7)

![Screenshot 2024-01-24 195310](https://github.com/boluadunbarin/configure-ad/assets/157642328/40159601-e29d-427d-86bc-cd1d5174a145)

![Screenshot 2024-01-24 195829](https://github.com/boluadunbarin/configure-ad/assets/157642328/610c51cb-9b0f-4aff-9995-08685ee6ba0a)

![Screenshot 2024-01-24 195924](https://github.com/boluadunbarin/configure-ad/assets/157642328/926c15d3-2e56-4320-9f1d-4d1271cea5a8)

![Screenshot 2024-01-24 200035](https://github.com/boluadunbarin/configure-ad/assets/157642328/e3c2ffa6-6ffd-45d2-a568-80a9517548d0)

![Screenshot 2024-01-24 200244](https://github.com/boluadunbarin/configure-ad/assets/157642328/1999ebf8-8617-4a70-ac03-0ab0755f174c)

![Screenshot 2024-01-24 200511](https://github.com/boluadunbarin/configure-ad/assets/157642328/2bee0d7a-aa62-4ec0-bceb-26a27d625011)

![Screenshot 2024-01-24 200609](https://github.com/boluadunbarin/configure-ad/assets/157642328/62d68869-5812-4a46-8ee4-67887bf5e6c1)

![Screenshot 2024-01-24 200654](https://github.com/boluadunbarin/configure-ad/assets/157642328/4c453896-8670-47d6-9b81-04757656f114)

![Screenshot 2024-01-24 200819](https://github.com/boluadunbarin/configure-ad/assets/157642328/09102939-6a62-4dd7-82ab-77733375b156)
