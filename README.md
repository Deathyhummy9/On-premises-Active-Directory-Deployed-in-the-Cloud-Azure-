<p align="center">
  <img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo" width="250"/>
</p>

# 🖥️ On-Premises Active Directory in the Cloud (Azure)

This project demonstrates how to deploy and configure an **on-premises Active Directory** environment in the cloud using **Microsoft Azure**.  
The lab simulates a realistic enterprise infrastructure where a Domain Controller manages authentication and a Windows client is joined to the domain.

---

## 🧰 Environments and Technologies Used

- Microsoft Azure (Virtual Machines / Compute)  
- Remote Desktop Protocol (RDP)  
- Active Directory Domain Services (AD DS)  
- Windows PowerShell

---

## 🖥️ Operating Systems Used

- Windows Server 2022  
- Windows 10 (21H2)

---

## 🧭 High-Level Deployment Steps

1. Provision infrastructure in Azure (Resource Group, VNet, Subnet)  
2. Deploy and configure the Domain Controller (DC)  
3. Deploy and configure a Windows Client  
4. Install and configure Active Directory Domain Services  
5. Create domain users and groups  
6. Join the client to the domain and verify  
7. Configure RDP access for domain users

---

## 🏗️ Step-by-Step Deployment & Configuration

### 1. Setup Domain Controller (DC-1)
<p>
<img width="1413" height="856" alt="Screenshot (112)" src="https://github.com/user-attachments/assets/3a64dc0d-8217-4226-bf7c-92484702ced8" />
<img width="1428" height="858" alt="Screenshot (113)" src="https://github.com/user-attachments/assets/9ea28785-462c-47f8-8327-9f95abea3dc6" />



</p>
<p>
- Create a Resource Group in Azure.  
- Create a Virtual Network and Subnet.  
- Deploy a Windows Server 2022 VM named `DC-1`.  
  - Username: `labuser`  
  - Password: `Cyberlab123!`  
- Set the NIC Private IP to static.  
- Log in to `DC-1` and disable Windows Firewall (for testing).
<br />

### 2. Setup Client (Client-1)
<img width="1425" height="856" alt="Screenshot (115)" src="https://github.com/user-attachments/assets/afdd9f13-b72d-4b52-987a-ef67f02e5cad" />
<img width="1684" height="1048" alt="Screenshot (117)" src="https://github.com/user-attachments/assets/3fff6ebe-75ea-4635-b579-75fb73c19543" />
<img width="1682" height="1051" alt="Screenshot (118)" src="https://github.com/user-attachments/assets/b544635f-b04e-4632-93a7-df7e729376cc" />

- Deploy a Windows 10 VM named `Client-1`.  
  - Username: `labuser`  
  - Password: `Cyberlab123!`  
- Attach it to the same VNet and region as `DC-1`.  
- Set Client-1’s DNS to DC-1’s Private IP.  
- Restart Client-1 from Azure Portal.  
- Log in and ping DC-1’s private IP.  
- Verify connectivity:
  powershell ipconfig /all

<p>
##3. Install Active Directory on DC-1
<img width="1689" height="1046" alt="Screenshot (119)" src="https://github.com/user-attachments/assets/195403f9-60ac-43fb-8925-2305bec24576" />

Log in to DC-1.
Install Active Directory Domain Services role.
Promote the server to a domain controller and create a new forest:
mydomain.com
Restart and log in as:

mydomain.com\labuser

##4. Create Domain Admin Account
<img width="1791" height="1080" alt="Screenshot (120)" src="https://github.com/user-attachments/assets/c06f1216-3620-4143-bc66-5fcf5c5df62e" />

Open Active Directory Users and Computers.

Create Organizational Units:
_EMPLOYEES
_ADMINS
Create user:
Username: jane_admin
Password: Cyberlab123$
Add jane_admin to Domain Admins group.
Log out and log back in as:
mydomain.com\jane_admin


##5. Join Client-1 to the Domain

Confirm DNS is pointing to DC-1 (already done).

Restart Client-1.
Log in as labuser (local admin).
Join Client-1 to:
mydomain.com
(Computer will restart.)

Log in to the Domain Controller and verify Client-1 appears in ADUC.

Create a new OU named _CLIENTS and move Client-1 object there.

##6. RDP for Non-Admin Users 

Log in to Client-1 as:

mydomain.com\jane_admin

Open System Properties → Remote Desktop.

Add Domain Users group to RDP permissions.

Now domain users can log in to Client-1 via Remote Desktop.
---
##Completion
Final result after completing this lab:

A fully functional Domain Controller (DC-1) on Windows Server 2022

A domain-joined Windows 10 client (Client-1)

Configured OUs and an administrative account (jane_admin)

Domain Users enabled for Remote Desktop access

Core on-premises Active Directory environment running in Azure

This is a fundamental project for anyone building a career in IT infrastructure 
