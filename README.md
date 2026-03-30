# 🖥️ Active Directory Home Lab

## Overview

This repository walks through the setup of an Active Directory home lab
using Oracle VirtualBox. The lab covers installing Active Directory Domain
Services, creating a domain, managing users and organizational units, and
joining client machines to the domain.

Completing this lab provides hands-on experience with Windows networking
and AD management, reinforcing practical IT skills in a controlled environment.

---

## 🧰 Lab Environment

| Field | Value |
|---|---|
| **Hypervisor** | Oracle VirtualBox |
| **Domain Controller** | Windows Server 2019 |
| **Client Machine** | Windows 10 (21H2) |
| **Domain** | mydomain.com |
| **Automation** | PowerShell |

---

## 🏗️ Lab Architecture

<img width="640" alt="Lab Architecture Overview" src="https://github.com/user-attachments/assets/a718e789-19f3-4b95-a3cf-c7cf8f311352" />

This diagram illustrates the logical design of the lab, built to simulate
a small enterprise Windows domain environment with centralized identity
and network services.

**Domain Controller (Windows Server 2019)**

Configured with two network interfaces:

| Interface | Purpose |
|---|---|
| External NIC | Outbound internet access |
| Internal NIC | Static IP 172.16.0.1/24 — serves the internal domain |

Services hosted on the Domain Controller:

| Service | Role |
|---|---|
| AD DS | Centralized authentication and user management |
| DNS | Internal name resolution |
| DHCP | IP assignment — scope 172.16.0.100–172.16.0.200 |
| RAS/NAT | Routes internal clients to the internet |
| PowerShell | Bulk user creation automation |

**Client Machine (Windows 10)**

Connected only to the internal network. Receives IP from DHCP and is
joined to the domain. Used to validate authentication, DNS, DHCP, and
Group Policy application.

---

## 📸 Lab Walkthrough

### 1. Active Directory Users and Computers

<img width="754" alt="AD Users and Computers" src="https://github.com/user-attachments/assets/85db8141-da7c-4f7e-af8a-69f013e74101" />

Confirms that `mydomain.com` is active and test user accounts have been
created, validating core AD functionality is operational.

---

### 2. Domain-Joined Client

<img width="1024" alt="Windows 10 Client Domain Join" src="https://github.com/user-attachments/assets/bf827dbe-5ae9-4d7d-a0a3-09fd7e7964a3" />

Confirms the Windows 10 client is joined to `mydomain.com`, validating
that DHCP, DNS, and domain authentication are functioning correctly.

---

### 3. Windows 10 IP & DNS Details

<img width="1024" alt="ipconfig Client1" src="https://github.com/user-attachments/assets/f4b240c8-5ff0-4ebd-9944-ce80d998a3d8" />

Validates that the client receives a DHCP-assigned IP, resolves the domain
controller via DNS, and can communicate with `DC01.mydomain.com`.

---

### 4. Registered Domain Computers

<img width="986" alt="Client1 in ADUC" src="https://github.com/user-attachments/assets/6d7d7abd-abca-4fbb-b88a-df1aa7a1c0a2" />

`CLIENT1` is listed in Active Directory, confirming it is joined to the
domain and centrally managed by the domain controller.

---

### 5. Ping Internal Client

<img width="1001" alt="Ping CLIENT1 Domain" src="https://github.com/user-attachments/assets/de93881e-51df-4704-b6fa-4201b504f6bd" />

`CLIENT1.mydomain.com` is reachable over the internal network, confirming
internal name resolution and network connectivity are fully operational.

---

## 🛠️ Skills Demonstrated

- Active Directory Domain Services installation and configuration
- DNS and DHCP setup and validation
- OU structure and user account management
- PowerShell automation for bulk user creation
- Client domain join and Group Policy validation
- RAS/NAT configuration for internal network routing
- End-to-end network troubleshooting (ipconfig, ping, nslookup)

---

## ✅ Conclusion

Fully functional Active Directory environment with a domain controller and
domain-joined client. Core services including authentication, DHCP, DNS,
and centralized management are all operational and validated end-to-end.
