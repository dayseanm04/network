# 🌐 Configuring DNS Lab

## 📘 Lab Overview

In this lab, I explored the operation and configuration of **Domain Name System (DNS)**. The lab demonstrates how devices use DNS to resolve **hostnames into IP addresses**, and how routers and PCs interact with external DNS servers.

## Topology For Reference

<img width="626" height="254" alt="Topology" src="https://github.com/user-attachments/assets/9f1ee94d-b9ae-46a5-ba7f-a24102688816" />


---


## 🎯 Lab Objectives
By completing this lab, you will be able to:

- ✅ Configure a **default route** to reach the Internet
- ✅ Configure PCs to use an external **DNS server**
- ✅ Configure a router to use DNS and local host entries
- ✅ Verify **name resolution** using ping
- ✅ Analyze DNS traffic in simulation mode

---

## 🧪 Lab Tasks

### 🧩 Task 1 – Configure a Default Route on R1

- Configure a **default route** so R1 can reach the Internet
- This allows DNS queries and external traffic to leave the network

**Note📌: DNS resolution will not work without proper routing.**

---

### 🧩 Task 2 – Configure DNS on PCs

- Configure **PC1, PC2, and PC3** to use **1.1.1.1** as their DNS server
- Verify DNS settings using command prompt

---

### 🧩 Task 3 – Configure DNS on R1

- Configure R1 to use **1.1.1.1** as its DNS server
- Create **local host entries** for:
  - R1
  - PC1
  - PC2
  - PC3
- Verify name resolution by pinging **PC1 by hostname** from R1

**Note📌: This demonstrates local name resolution vs external DNS.**

---

### 🧩 Task 4 – Analyze DNS Resolution (Simulation Mode)

⚠️ **USE SIMULATION MODE**

- From **PC1**, ping **youtube.com by name**
- Observe and analyze:
  - DNS Query
  - DNS Response


**Note📌: This step shows the full process of hostname resolution and packet flow.**


---

## ✍️ Author Information

**Name:** *Daysean Mensah*  
**Course/Program:** *Cisco CCNA Studies*  
**Lab completion date:** December 30 2025.
