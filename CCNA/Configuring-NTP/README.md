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



