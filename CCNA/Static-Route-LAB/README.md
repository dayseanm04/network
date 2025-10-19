# Configuring Static Route Lab

## 📘 Objective
The objective of this lab is to configure and verify **static routing** on Cisco routers to enable communication between end devices on different networks. The lab focuses on:

- Assigning IP addresses to router interfaces and PCs  
- Configuring default gateways for end devices  
- Implementing static routes to ensure full connectivity across the network  

---

## 🧩 Network Overview
The topology consists of **three routers (R1, R2, R3)** and **two PCs (PC1, PC2)** connected through multiple subnets. Each router has interfaces configured with appropriate IP addresses to create point-to-point links, while PCs are assigned IP addresses and gateways within their respective subnets.

| Device | Interface | IP Address | Subnet Mask | Description |
|---------|------------|-------------|--------------|--------------|
| R1 | G0/1 | 192.168.1.254 | 255.255.255.0 | LAN for PC1 |
| R1 | G0/0 | 192.168.12.1 | 255.255.255.0 | Link to R2 |
| R2 | G0/0 | 192.168.12.2 | 255.255.255.0 | Link to R1 |
| R2 | G0/1 | 192.168.13.2 | 255.255.255.0 | Link to R3 |
| R3 | G0/0 | 192.168.13.3 | 255.255.255.0 | Link to R2 |
| R3 | G0/1 | 192.168.3.254 | 255.255.255.0 | LAN for PC2 |
| PC1 | NIC | 192.168.1.1 | 255.255.255.0 | Gateway: 192.168.1.254 |
| PC2 | NIC | 192.168.3.1 | 255.255.255.0 | Gateway: 192.168.3.254 |

---

## ⚙️ Lab Tasks

### Task 1: Configure Network Devices
- Assign hostnames and IP addresses to routers  
- Configure interfaces and enable them  
- Set IP addresses and default gateways for PCs  

### Task 2: Implement Static Routes
- Configure static routes on each router to enable connectivity between all networks  
- Verify routing tables and test communication using the `ping` command  

---

## 🧠 Summary
This lab demonstrates how static routes are manually configured to define paths between networks. Once routing was properly set up:

- PC1 (192.168.1.1) successfully pinged PC2 (192.168.3.1)  

The configuration achieved **two-way reachability**, confirming that static routing was implemented successfully.

---

## 🧾 Verification
- Verified routing with `show ip route` on each router  
- Successful ping tests between PC1 and PC2 confirmed network connectivity  

---

## ✍️ Author Information

**Name:** *Daysean Mensah*  
**Course/Program:** *Cisco CCNA Studies*  
