# ⏱️ Configuring NTP (Network Time Protocol)

## 📌 Lab Overview
In this lab, I configured **Network Time Protocol (NTP)** to ensure consistent and accurate time synchronization across multiple routers.  

Accurate time is critical for **logs, troubleshooting, authentication, and security auditing** in real-world networks.

This lab covers **manual clock configuration**, **time zones**, **external NTP servers**, **NTP master configuration**, **authentication**, and **hardware calendar updates** using Cisco Packet Tracer.

## Topology For Refernece

<img width="648" height="256" alt="topology" src="https://github.com/user-attachments/assets/e30bc4fe-1d0b-480f-82fd-509165d35916" />

---

## 🎯 Objectives
- Configure and verify system clocks on multiple routers  
- Apply correct time zone settings  
- Synchronize a router with an external NTP server  
- Configure an internal NTP master with authentication  
- Ensure routers update their hardware calendars using NTP  

---

## 📋 Lab Tasks

### 🕒 Task 1: Configure Software Clock (UTC)
- Manually set the **software clock** on **R1, R2, and R3**
- Date & Time: **12:00:00 Dec 30 2020 (UTC)**
- Verify clock configuration on all routers

---

### 🌎 Task 2: Configure Time Zone (EST)
- Configure the **time zone** on **R1, R2, and R3**
- Time zone must match the **local system time**
- Verify updated time display

---

### 🌐 Task 3: Configure External NTP Server
- Configure **R1** to synchronize with **NTP server `1.1.1.1`**
- Verify NTP synchronization status
- Identify:
  - **Stratum level of 1.1.1.1**
  - **Stratum level of R1**
 
 ---


### 🧩 Task 4 & 5: Configure Internal NTP Master with Authentication

### ⚠️ Packet Tracer limitation: 
- The **ntp source** command is **not available**, so **physical interface IP addresses** are used instead.

#### Task 4:
- Configure **R1 as a Stratum 8 NTP Master**
- Enable **NTP authentication**
- Synchronize **R2 and R3** to **R1**
- Verify successful authentication and synchronization

#### Task 5:
- Configure NTP to **update hardware calendars**
- Note: Hardware calendar **cannot be viewed** in Packet Tracer

### (Task 5 is completed as part of Task 4)

---

## ✍️ Author Information

**Name:** *Daysean Mensah*  
**Course/Program:** *Cisco CCNA Studies*  
**Lab completion date:** December 27 2025.
