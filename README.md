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
<img width="977" alt="Screenshot 2023-11-30 at 1 52 50 AM" src="https://github.com/reginacuenta/active-directory/assets/150301999/5e26ffa8-7d63-4102-aaaf-39571d9b054f">
</p>
<p>
Create a employee organizational unit.
</p>
<br />

<p>
<img width="909" alt="Screenshot 2023-11-30 at 1 53 55 AM" src="https://github.com/reginacuenta/active-directory/assets/150301999/aef6663d-9d6e-4990-8fd9-07b101bde8bf">
</p>
<p>
Create an admin organizational unit.
</p>
<br />

<p>
<img width="999" alt="Screenshot 2023-11-30 at 6 19 16 PM" src="https://github.com/reginacuenta/active-directory/assets/150301999/78374ad6-d45c-4371-8078-f341580f9049">
</p>
<p>
Create an admin account.
</p>
<br />

<p>
<img width="992" alt="Screenshot 2023-11-30 at 6 20 14 PM" src="https://github.com/reginacuenta/active-directory/assets/150301999/523e7a80-e561-451d-a7e1-e8fbab179ca5">
</p>
<p>
Include jane in domain admins.
</p>
<br />

<p>
<img width="911" alt="Screenshot 2023-11-30 at 6 21 31 PM" src="https://github.com/reginacuenta/active-directory/assets/150301999/1987a4fe-e7d3-40f8-af58-e0d99d4d659c">
</p>
<p>
Sign in as jane_admin within mydomain.com.
<br />

<p>
<img width="1033" alt="Screenshot 2023-11-30 at 6 33 07 PM" src="https://github.com/reginacuenta/active-directory/assets/150301999/0ee26a44-5c2f-489c-a154-f26a04a237e7">

</p>
<p>
From the Azure Portal, set Client-1’s DNS settings to the DC’s Private IP address.

</p>
<br />

<p>
<img width="1252" alt="Screenshot 2023-11-30 at 6 35 20 PM" src="https://github.com/reginacuenta/active-directory/assets/150301999/d48c811c-4470-47c4-b0c5-4264b81670e8">

</p>
<p>
From the Azure Portal, restart Client-1.

</p>
<br />

<p>
<img width="1285" alt="Screenshot 2023-11-30 at 8 04 43 PM" src="https://github.com/reginacuenta/active-directory/assets/150301999/7b5d8a36-319f-41b5-a027-5da99aa8a9ba">

</p>
<p>
Login to Client-1 (Remote Desktop) as the original local admin (labuser) and join it to the domain (computer will restart).
</p>
<br />

<p>
<img width="1237" alt="Screenshot 2023-11-30 at 8 40 17 PM" src="https://github.com/reginacuenta/active-directory/assets/150301999/9065b15c-ff5d-4d11-8db0-6e9132a9bc28">

</p>
<p>
Login to the Domain Controller (Remote Desktop) and verify Client-1 shows up in Active Directory Users and Computers (ADUC) inside the “Computers” container on the root of the domain.
</p>
<br />

<p>
<img width="1245" alt="Screenshot 2023-11-30 at 8 40 29 PM" src="https://github.com/reginacuenta/active-directory/assets/150301999/7793e495-4949-4b5a-a069-b1224da62592">
</p>
<p>
Log into Client-1 as mydomain.com\jane_admin and open system properties.

</p>
<br />

<p>
<img width="1260" alt="Screenshot 2023-11-30 at 8 41 05 PM" src="https://github.com/reginacuenta/active-directory/assets/150301999/3dfbfb14-da30-442c-bca2-f2a67d1d2a35">
</p>
<p>
Allow “domain users” access to remote desktop.

</p>
<br />

<p>
<img width="1270" alt="Screenshot 2023-11-30 at 9 06 45 PM" src="https://github.com/reginacuenta/active-directory/assets/150301999/eb6dbaf6-146d-4bdd-8846-5189961a17c8">

</p>
<p>
Login to DC-1 as jane_admin.

</p>
<br />

<p>
<img width="1256" alt="Screenshot 2023-11-30 at 9 09 11 PM" src="https://github.com/reginacuenta/active-directory/assets/150301999/6b6610c5-2567-4023-9aee-5b5dc1627b8e">

</p>
<p>
Open PowerShell_ise as an administrator. Create a new File and paste the contents of the script into it.
</p>
<br />

<p>
<img width="1097" alt="Screenshot 2023-11-30 at 8 43 20 PM" src="https://github.com/reginacuenta/active-directory/assets/150301999/d8ad67da-429f-4433-b846-e3a3a85c5e02">

</p>
<p>
Login as one of the created users from the script.
</p>
<br />

<p>
<img width="1266" alt="Screenshot 2023-11-30 at 9 13 11 PM" src="https://github.com/reginacuenta/active-directory/assets/150301999/78d7f59c-8898-4412-a181-a318a45b8a41">

</p>
<p>
In DC-1, you can reset the password, disable an account and enable an account.
</p>
<br />

