# 📶 Configure WLANs Using Cisco Wireless LAN Controller

## 📌 Summary
This lab focuses on configuring a **wireless network using a Cisco Wireless LAN Controller (WLC)**.  
I will access the **WLC GUI**, create **dynamic interfaces**, configure **Internal and Guest WLANs**, and verify that a **wireless client can successfully connect** through a Wireless access point (WAP).

The goal is to understand how centralized wireless management works using a WLC.

---

## 🎯 Lab Objectives

By completing this lab, you will be able to:
- Access and navigate the **Cisco 3504 Wireless Controller GUI**
- Understand the **current state of the wireless network**
- Configure **dynamic interfaces** for different WLANs
- Create **secure WLANs using WPA2-PSK**
- Verify **wireless client connectivity**

## Topology For Reference

<img width="491" height="251" alt="topology" src="https://github.com/user-attachments/assets/72d0bdd5-e278-4cca-9727-160600a81eb2" />

---

## 🧪 Lab Tasks Overview

### 🌐 Task 1 – Access and Explore the WLC GUI

- Use **PC1** to access the **WLC1 GUI**
- Connect using **HTTPS**
- Log in with:
  - **Username:** `admin`
  - **Password:** `Cisco123`
- Explore the WLC tabs and dashboards
- Observe the current network status (APs, WLANs, interfaces)

📌 *Purpose:* Become familiar with the WLC interface and understand how the wireless network is managed.

---

### 🔧 Task 2 – Configure Dynamic Interfaces for Internal and Guest WLANs

- Create separate **dynamic interfaces** on the WLC
- Assign each interface to the correct VLAN and IP configs
- Prepare the WLC for multiple WLANs

📌 *Purpose:* Support network segmentation for Internal and Guest wireless traffic.

---

## ✍️ Author Information

**Name:** *Daysean Mensah*  
**Course/Program:** *Cisco CCNA Studies*  
**Lab completion date:** january 14 2026.
