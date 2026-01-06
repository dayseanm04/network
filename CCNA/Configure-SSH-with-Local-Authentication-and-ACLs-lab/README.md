# 🔐 Configure SSH with Local Authentication and ACLs Lab

## 📌 Lab Overview
In this lab, I configured **secure remote management using SSH** on a newly added access switch (**SW2**).  
The lab begins with **initial switch setup via the console**, then I applied **local authentication**, and the I finally enabled **SSH-only remote access** restricted by an **access control list (ACL)**.

This configuration reflects real-world best practices for **secure device management**, replacing insecure protocols like Telnet with **encrypted SSH access**.

## Reference Topology

<img width="545" height="224" alt="topology" src="https://github.com/user-attachments/assets/ae47e659-6807-4ae7-9c97-e89aa8e4ebba" />

---

## 🎯 Objectives
- Perform initial switch configuration using the **console**
- Secure console access with **local authentication**
- Configure **SSH remote access** with RSA encryption
- Restrict SSH access using an **ACL**
- Verify that only authorized hosts can manage the switch

---

## 📋 Lab Tasks

### 🖥️ Task 1 - Initial Switch Configuration (Console)
- Connect **Laptop1** to **SW2’s console port**
- Configure:
  - Hostname
  - Enable secret
  - Local user account
  - VLAN 1 SVI IP address
  - Default gateway

---

### 🔒 Task 2 - Secure Console Access
- Configure **console line security** on SW2
- Enable **local authentication**
- Set an **exec timeout of 5 minutes**

---

### 🌐 Task 3 - Secure Remote Access with SSH + ACLs
- Configure **SSH** on SW2 with:
  - Domain name
  - RSA keys (2048-bit)
  - Local user authentication
  - SSH-only access (no Telnet)
- Create and apply an **ACL** to restrict SSH access to **PC1 only**
- Verify successful SSH access from PC1 and denied access from other devices

---

## ✍️ Author Information

**Name:** *Daysean Mensah*  
**Course/Program:** *Cisco CCNA Studies*  
**Lab completion date:** january 3 2026.
