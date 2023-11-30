<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://youtu.be/ix__X_49NnQ)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Setup resources in Azure
- Ensure connectivity between the client and domain controller
- Install active directory
- Create an admin and normal user account in Active Directory
- Join client-1 to your domain
- Create remote desktop for non-administrative users on client-1
- create more additional users and attempt to log into client-1 with one of the users

<h2>Deployment and Configuration Steps</h2>

<p>
  <img width="1122" alt="Screenshot 2023-11-30 at 1 32 07 AM" src="https://github.com/reginacuenta/active-directory/assets/150301999/29a89b64-9187-44da-b13d-aa34fe1175bd">

</p>
<p>
Create client-1 virtual machine
</p>
<br />

<p>
<img width="1212" alt="Screenshot 2023-11-30 at 1 32 23 AM" src="https://github.com/reginacuenta/active-directory/assets/150301999/b25b824a-8557-40db-820c-6e604065e389">
</p>
<p>
Create DC-1 virtual machine. Change Domain Controller’s NIC Private IP address to be static. Ensure that both VMs are in the same virtual network.
</p>
<br />

<p>
<img width="996" alt="Screenshot 2023-11-30 at 1 40 27 AM" src="https://github.com/reginacuenta/active-directory/assets/150301999/22814547-f978-491e-9747-5739bb55e836">
</p>
<p>
Ping DC-1's private IP address. Check back to client-1 if the ping succeed.
</p>
<br />

<p>
<img width="1221" alt="Screenshot 2023-11-30 at 1 42 31 AM" src="https://github.com/reginacuenta/active-directory/assets/150301999/e98f87c4-e5d9-457d-bd4d-6c63b211cd88">
</p>
<p>
Install active directory.
</p>
<br />

<p>
<img width="1067" alt="Screenshot 2023-11-30 at 1 43 47 AM" src="https://github.com/reginacuenta/active-directory/assets/150301999/3852f198-9333-47e0-805a-dc348ce66242">
</p>
<p>
Create a domain name.
</p>
<br />

<p>
<img width="736" alt="Screenshot 2023-11-30 at 1 44 39 AM" src="https://github.com/reginacuenta/active-directory/assets/150301999/fbe1ca8f-e7dd-4667-ada6-b7f8276fec62">
</p>
<p>
Sign in with username and domain name.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
