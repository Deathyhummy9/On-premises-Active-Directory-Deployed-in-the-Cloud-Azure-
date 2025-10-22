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
<img width="1415" height="891" alt="Screenshot (112)" src="https://github.com/user-attachments/assets/0bd3b3cd-a153-4251-9324-893fc0890eab" />
<img width="1428" height="916" alt="Screenshot (113)" src="https://github.com/user-attachments/assets/c7fac4f1-1fa3-4b7f-a661-a7a8c3271899" />


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
