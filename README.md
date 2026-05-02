\# 🖥️ Windows Server 2019 Administration Project



\## 📌 Overview



This project demonstrates the deployment and administration of a complete \*\*Windows Server 2019 Core environment\*\* using \*\*PowerShell\*\* in a virtualized setup.



The objective is to simulate a real-world enterprise infrastructure by configuring essential system and network services.



\---



\## 🎯 Objectives



\* Install and configure Windows Server 2019 Core

\* Manage files and directories using PowerShell

\* Create and manage users and groups (Local \& Active Directory)

\* Configure network services:



&#x20; \* DNS Server

&#x20; \* DHCP Server

&#x20; \* Web Server (IIS)

\* Apply security best practices and permissions (NTFS \& ACL)



\---



\## 🧰 Technologies Used



\* Windows Server 2019 Core

\* PowerShell

\* Oracle VirtualBox

\* Active Directory Domain Services (AD DS)

\* DNS / DHCP / IIS



\---



\## 🏗️ Project Architecture



\* Virtual Machine hosted on VirtualBox

\* Server configured in \*\*Core mode (no GUI)\*\*

\* Network services deployed and tested

\* Domain environment simulated using Active Directory



\---



\## ⚙️ Installation \& Setup



\### 1. Prerequisites



\* VirtualBox installed

\* Windows Server 2019 ISO

\* Minimum:



&#x20; \* 2 GB RAM (4 GB recommended)

&#x20; \* 40 GB storage



\---



\### 2. Create Virtual Machine



\* Type: Windows

\* Version: Windows Server 2019 (64-bit)

\* RAM: 2–4 GB

\* CPU: 2–4 cores



\---



\### 3. Install Windows Server Core



\* Boot VM with ISO

\* Follow installation steps

\* Set Administrator password



\---



\### 4. Initial Configuration (PowerShell)



```powershell

sconfig

```



\* Rename server

\* Configure IP address

\* Enable Remote Desktop

\* Set updates



\---



\## 🌐 Network Configuration



\### Static IP



```powershell

New-NetIPAddress -InterfaceAlias "Ethernet" -IPAddress 192.168.1.100 -PrefixLength 24 -DefaultGateway 192.168.1.1

```



\### DNS Configuration



```powershell

Set-DnsClientServerAddress -InterfaceAlias "Ethernet" -ServerAddresses ("192.168.1.100", "8.8.8.8")

```



\---



\## 👥 User \& Group Management



\### Create Local User



```powershell

New-LocalUser -Name "user1" -Password (ConvertTo-SecureString "Password123" -AsPlainText -Force)

```



\### Create AD User



```powershell

New-ADUser -Name "User AD" -Enabled $true

```



\---



\## 📁 File Management



\* Create files and folders using PowerShell

\* Modify, move, and delete resources

\* Apply NTFS permissions using `icacls`



\---



\## 🔐 Permissions \& Security



\* ACL (Access Control Lists)

\* Principle of least privilege

\* Group-based permission management



\---



\## 🌍 Network Services



\### 🔹 DNS Server



\* Zone creation

\* A and CNAME records



\### 🔹 DHCP Server



\* IP range configuration

\* Automatic IP assignment



\### 🔹 IIS Web Server



\* Install IIS role

\* Host a basic website



\---



\## 🧪 Testing \& Validation



\* Verify IP configuration

\* Test DNS resolution

\* Check DHCP leases

\* Access web server via browser



\---



\## 📊 Key Learnings



\* System administration without GUI (Core mode)

\* PowerShell automation

\* Network services deployment

\* Security and permissions management



\---



\## 📁 Repository Structure



```

/docs        -> Project report (PDF)

/scripts     -> (Optional future PowerShell scripts)

/images      -> (Optional screenshots)

/README.md

```



\---



\## 📌 Future Improvements



\* Add automation scripts

\* Add screenshots and demos

\* Dockerize services (advanced)

\* Monitoring \& logging



\---



\## 👩‍💻 Authors



\* Chaima Charif

\* Team Members



\---



\## 📄 License



This project is for academic and educational purposes.



