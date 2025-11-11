#  Active Directory Lab  IT Help Desk  Project

##  Lab Overview

| Component | Details |
|------------|----------|
| **Hypervisor** | Oracle VirtualBox |
| **Server OS** | Windows Server 2022 |
| **Client OS** | Windows 10 |
| **Domain** | ablab.local |
| **Server Hostname** | AD-SERVER |
| **Client Hostname** | CLIENT01 |
| **Network Type** | Internal Network (ablab) |
| **Roles Installed** | AD DS, DNS, File Services |
| **Purpose** | Simulate enterprise Active Directory environment with domain-joined clients and GPO management. |


---

##  Setup Steps (Highlights)

### 1. Virtual Machine Configuration
- Created VM in VirtualBox for **Windows Server 2022**  
  ![VirtualBox VM Overview – WinServer2022](Screenshots/VirtualBox%20VM%20Overview%20–%20WinServer2022.png)
- Configured **Internal Network** named `ablab`  
  ![VirtualBox Internal Network Configuration](Screenshots/VirtualBox%20Internal%20Network%20Configuration.png)

---

### 2. Network Setup
- Assigned **static IP** on the Server (192.168.1.50)  
  ![Static IP Setup (AD-SERVER)](Screenshots/Static%20IP%20Setup%20(AD-SERVER).png)
- Verified DNS loopback configuration  
  ![Server Manager — Domain Association](Screenshots/Server%20Manager%20—%20Domain%20Association.png)

---

### 3. Active Directory and DNS Installation
- Installed **AD DS** and **DNS Server roles**  
  ![Installing Active Directory Domain Services and DNS Roles](Screenshots/Installing%20Active%20Directory%20Domain%20Services%20and%20DNS%20Roles.png)

---

### 4. Domain Configuration
- Configured the domain as **ablab.local**  
  ![System Properties – Domain Setup (AD-SERVER)](Screenshots/System%20Properties%20–%20Domain%20Setup%20(AD-SERVER).png)
- Verified domain using PowerShell  
  ![PowerShell Domain Verification](Screenshots/PowerShell%20Domain%20Verification.png)

---

### 5. Organizational Units (OUs) and Security Groups
- Created `IT-Admins` OU and **HelpDesk_Admins** group  
  ![Active Directory — HelpDesk_Admins Security Group](Screenshots/Active%20Directory%20—%20HelpDesk_Admins%20Security%20Group.png)
- Added members to the group  
  ![Active Directory – HelpDesk_Admins Group Membership](Screenshots/Active%20Directory%20–%20HelpDesk_Admins%20Group%20Membership.png)
- Verified domain computers  
  ![Active Directory — Domain Controllers OU](Screenshots/Active%20Directory%20—%20Domain%20Controllers%20OU.png)
  ![Active Directory — Computers OU](Screenshots/Active%20Directory%20—%20Computers%20OU.png)

---

### 6. Group Policy Configuration
- Opened **Group Policy Management Console (GPMC)**  
  ![Group Policy Management — Domain Overview](Screenshots/Group%20Policy%20Management%20—%20Domain%20Overview.png)
- Linked multiple **Group Policy Objects (GPOs)**  
  ![Group Policy Management – Linked Group Policies](Screenshots/Group%20Policy%20Management%20–%20Linked%20Group%20Policies.png)
- Configured **Wallpaper Policy**  
  ![Group Policy Management Editor — Wallpaper Policy](Screenshots/Group%20Policy%20Management%20Editor%20—%20Wallpaper%20Policy.png)
- Added **Mapped Drive (W:)**  
  ![Group Policy Management Editor – Mapped Network Drive](Screenshots/Group%20Policy%20Management%20Editor%20–%20Mapped%20Network%20Drive.png)

---


##  Author
**Mayedson Pierre**  

