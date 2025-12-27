# 🧠 Reflection - Configuring NTP Lab

## 📌 Lab Summary
In this lab, I configured **Network Time Protocol (NTP)** to provide accurate and consistent time synchronization across multiple routers. I started the lab of by manually setting the **software clock** and **time zone** on each device to establish a baseline. I then configured **R1 as an NTP client** using an external Internet time server and verified synchronization and **stratum levels**.

Finally, I configured **R1 as an internal NTP master (Stratum 8)** and securely synchronized **R2 and R3** using **NTP authentication**. The lab concluded with configuring NTP to update the **hardware calendar** on all routers, ensuring long-term time accuracy even after reboots.

## Topology For Refernece

<img width="648" height="256" alt="topology" src="https://github.com/user-attachments/assets/e30bc4fe-1d0b-480f-82fd-509165d35916" />

---

## 📘 What I Learned
- How to manually configure and verify the **software clock** on Cisco routers  
- The importance of setting the correct **time zone** for accurate logs and timestamps  
- How NTP uses **stratum levels** to determine time accuracy and hierarchy  
- How to configure a router as an **NTP client** using an external time source  
- How to configure an **internal NTP master** for a private network  
- How **NTP authentication** improves security by preventing unauthorized time sources  

---


