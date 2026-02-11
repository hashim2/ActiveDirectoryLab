<h1> - Active Directory Home Lab</h1>

 

<h2>Description</h2>
This repository walks through the setup of an Active Directory home lab using Oracle VirtualBox. The lab covers core concepts such as installing Active Directory Domain Services, creating a domain, managing users and organizational units, and joining client machines to the domain.
Completing this lab provides hands-on experience with Windows networking and AD management, making it a great way to practice and reinforce practical IT skills in a controlled environment.

<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Oracle Virtual Box</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)
- <b>Server 2019

<h2>Program walk-through:</h2>
<img width="640" height="360" alt="Internet" src="https://github.com/user-attachments/assets/a718e789-19f3-4b95-a3cf-c7cf8f311352" />

**LAB ARCHITECTURE OVERVIEW**

- This diagram illustrates the logical design of my Active Directory home lab, built to simulate a small enterprise Windows domain environment with centralized identity and network services.
The lab consists of a Windows Server 2019 Domain Controller and a Windows 10 client hosted in VirtualBox and connected through an internal virtual network.

**DOMAIN CONTROLLER (WINDOWS SERVER 2019)**

The Domain Controller is configured with two network interfaces:

- External NIC (Internet) providing outbound internet access

- Internal NIC (Internal Network) using a static IP address (172.16.0.1/24) to serve the internal domain

**THE DOMAIN CONTROLLER HOSTS THE FOLLOWING SERVICES:**

- Active Directory Domain Services (AD DS) for centralized authentication and management
- DNS for internal name resolution
- DHCP with a single scope (172.16.0.100–172.16.0.200) for client IP assignment
- Routing and Remote Access (RAS/NAT) to allow internal clients internet access
- PowerShell automation used to bulk-create test users

**CLIENT MACHINE (WINDOWS 10)**

- The Windows 10 client is connected only to the internal network, receives its IP configuration from DHCP, and is joined to the domain. It is used to validate authentication, DNS resolution, DHCP leasing, and Group Policy application.

**DESIGN PURPOSE**

- This architecture mirrors a common enterprise Active Directory deployment by separating external and internal traffic while maintaining centralized domain services.</p>




**ACTIVE DIRECTORY USERS AND COMPUTERS (ADUC)**

<img width="754" height="530" alt="AD users and computers" src="https://github.com/user-attachments/assets/85db8141-da7c-4f7e-af8a-69f013e74101" />

- This view confirms the domain mydomain.com is active and that test user accounts have been created. It demonstrates that the lab’s core AD functionality is operational.


**DOMAIN-JOINED CLIENT**

<img width="1024" height="728" alt="Win10 Client" src="https://github.com/user-attachments/assets/bf827dbe-5ae9-4d7d-a0a3-09fd7e7964a3" />

- This confirms the Windows 10 client is joined to the mydomain.com domain, validating that DHCP, DNS, and domain authentication are functioning correctly.


**WINDOWS 10 IP & DNS DETAILS**
<img width="1024" height="728" alt="ipconfig client1" src="https://github.com/user-attachments/assets/f4b240c8-5ff0-4ebd-9944-ce80d998a3d8" />

- This validates that the Windows 10 client receives DHCP configuration, resolves the domain controller via DNS, and can communicate with DC01.mydomain.com, confirming core network functionality of the lab.

**REGISTERED DOMAIN-COMPUTERS**

<img width="986" height="550" alt="Client1 ADUC" src="https://github.com/user-attachments/assets/6d7d7abd-abca-4fbb-b88a-df1aa7a1c0a2" />

- The Windows 10 client CLIENT1 is listed in Active Directory, confirming it is joined to the domain and centrally managed by the domain controller.

**PING INTERNAL CLIENT**

<img width="1001" height="552" alt="ping client 1 domain" src="https://github.com/user-attachments/assets/de93881e-51df-4704-b6fa-4201b504f6bd" />

- **This confirms that internal name resolution and network connectivity are working in the lab, with CLIENT1.mydomain.com reachable over the internal network.**


**CONCLUSION**
- This lab demonstrates a fully functional Active Directory environment with a domain controller and a domain-joined client. Core services including authentication, DHCP, DNS, and centralized management are operational, validating end-to-end AD functionality.

  <!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
