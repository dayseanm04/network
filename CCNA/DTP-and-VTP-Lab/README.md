## 🧠 Dynamic Trunking Protocol & VLAN Trunking Protocol

This lab focuses on disabling **Dynamic Trunking Protocol (DTP)** and configuring **VLAN Trunking Protocol (VTP)** between multiple switches to practice VLAN management, trunk configuration, and DTP negotiation control.

---

## Topology For Reference
<img width="642" height="304" alt="Topology" src="https://github.com/user-attachments/assets/2c7ec9fb-46be-43c9-9715-8c7ff7954117" />

---

## 📋 Overview

In this lab,I configured multiple Cisco switches were configured to:
- Establish trunk connections between switches 🔗  
- Manage VLAN using VTP 🗂️  
- Assign access ports to the correct VLANs for connected hosts 💻  

The lab demonstrates how VTP operates in **server**, **client**, and **transparent** modes, and how **DTP** can be disabled to control trunk negotiation.

---

## 🧰 Devices Used
- 3 Cisco 2960-24TT switch (SW2)
- 9 PCs (PC1–PC9)  

---

## ⚙️ Tasks Completed

### 🧩 Task 1: Trunk Configuration & DTP Disable
- Configured trunk ports on SW1, SW2, and SW3.
- Disabled **DTP** using the `switchport nonegotiate` command.
- Verified **administrative** and **operational** mode of each interface with: `show interfaces g0/1 switchport`

### 🌐 Task 2: VTP Domain & VLAN Creation
- Configured **SW1** as the **VTP Server** with the domain `CCNA`.
- Created VLANs **10**, **20**, and **30** on SW1.
- Verified that VLANs were automatically propagated to SW2 and SW3.

### 🧱 Task 3: VTP Transparent Mode
- Configured **SW2** as **VTP Transparent**.
- Created **VLAN 40** on SW2.
- Verified VLAN 40 was **not** added to SW1 or SW3 VLAN databases (as expected).

### 📡 Task 4: VTP Client Mode
- Configured **SW3** as **VTP Client**.
- Attempted to create **VLAN 50** on SW3, which is not allowed (client mode cannot add VLANs).
- Confirmed VLAN synchronization occurs only from the VTP server (SW1).

### 💼 Task 5: Access Ports & VLAN Assignment
- Manually assigned switchports connected to PCs into their appropriate VLANs.
- Configured them as **access ports**.
- Verified DTP was **disabled** on all access ports

 ---

  
| VLAN | Network Address | Assigned Devices |
|------|------------------|------------------|
| VLAN 10 | 10.0.0.0/26 | PC1, PC2, PC5 |
| VLAN 20 | 10.0.0.64/26 | PC8, PC9 |
| VLAN 30 | 10.0.0.128/26 | PC6, PC7 |
| VLAN 40 | 10.0.0.192/26 | PC3, PC4 |

---

## 🧩 Summary

In this lab, I successfully applied key VLAN and trunking concepts, including:
- **DTP** allows dynamic negotiation of trunk links but can be disabled for security.
- **VTP** simplifies VLAN management across multiple switches by synchronizing VLAN information.
- Each **VTP mode** has a specific role:
- 🖥️ **Server:** Creates and distributes VLANs.
- 📦 **Client:** Receives VLANs from the server.
- 🧱 **Transparent:** Maintains its own VLANs locally and doesn’t propagate them.

By completing this lab, I learned how to:
- Managing VLANs efficiently using VTP.
- Controlling trunk negotiation with DTP.
- Properly assigning access ports to their respective VLANs.
