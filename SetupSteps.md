📘 SetupSteps.md

Windows Server 2022 Active Directory Lab — Step-by-Step Configuration

🧩 Overview

This lab demonstrates how to set up an Active Directory Domain Services (AD DS) environment using Windows Server 2022, complete with DNS, Group Policy, and domain client integration.
It’s designed for IT students, Help Desk technicians, and aspiring System Administrators to gain hands-on experience with enterprise-level Windows Server management.

⚙️ 1. Virtual Machine Setup (VirtualBox)

Open Oracle VirtualBox Manager.


Create a new virtual machine:

Name: WinServer2022

Type: Microsoft Windows

Version: Windows Server 2022 (64-bit)

Memory: 2 GB minimum

Virtual Disk: 60 GB (VDI, dynamically allocated)

Configure Network Adapter:

Adapter 1 → Attached to: Internal Network

Name: ablab

Promiscuous Mode: Deny

Check ✅ Virtual Cable Connected


🌐 2. Configure Network Settings (Server)

Inside Windows Server 2022, open Network Connections → Ethernet → Properties → IPv4.

Assign a static IP to the domain controller:

IP Address: 192.168.1.50
Subnet Mask: 255.255.255.0
Default Gateway: 192.168.1.1
Preferred DNS: 127.0.0.1


🧱 3. Rename Server and Join Domain

Open System Properties → Computer Name → Change

Rename the computer to:

AD-SERVER


Domain will be configured as ablab.local


🧩 4. Install Active Directory and DNS Roles

Open Server Manager → Add Roles and Features.

Select:

Active Directory Domain Services (AD DS)

DNS Server


After installation, promote the server to a Domain Controller and create the domain:

ablab.local

🖥️ 5. Verify Domain Configuration

Open Server Manager → Local Server to confirm the domain.


Or verify via PowerShell:

systeminfo | findstr /B /C:"Domain"


🧑‍💻 6. Active Directory Users and Computers Setup

Open Active Directory Users and Computers (ADUC).

Verify the Domain Controller (AD-SERVER) under the “Domain Controllers” OU.


Create a new Computer Object for your client machine (CLIENT01).


Create a new Security Group called HelpDesk_Admins.


Add users (e.g. John Doe) to the group.


🧭 7. Group Policy Management

Open Group Policy Management Console (GPMC).


Review and manage linked Group Policy Objects (GPOs):

Default Domain Policy

Workstation Security Policy

Experience Settings


🖼️ 8. Configure Group Policy Editor (GPO Settings)

Example: Create a Desktop Wallpaper Policy

Path: User Configuration → Administrative Templates → Desktop → Desktop Wallpaper

State: Enabled

Path: \\AD-SERVER\Wallpapers\home.jpg


Example: Map a Network Drive (W:) for all users

Path: User Configuration → Preferences → Windows Settings → Drive Maps

Action: Update

Location: \\AD-SERVER\Wallpapers


🧩 9. Client Machine Setup (CLIENT01)

On your Client VM, configure its VirtualBox network to the same internal network (ablab).


Join the client to the domain:

Domain: ablab.local


Confirm the client appears in ADUC → Computers OU.

✅ 10. Validation

Ensure domain logins work from the client machine.

Verify Group Policy settings apply correctly (wallpaper, mapped drives).

Test permissions for HelpDesk_Admins group.

🧠 Conclusion

You now have a fully functional Active Directory environment with DNS, GPOs, and domain-joined clients — perfect for IT practice labs, troubleshooting exercises, or resume portfolio projects.
