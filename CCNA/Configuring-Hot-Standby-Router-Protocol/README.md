# Configuring HSRP Lab 🔁🛡️

## 📌 Summary
This lab focuses on configuring and testing **HSRPv2 (Hot Standby Router Protocol)** to provide **default gateway redundancy** for end devices.  
You will verify connectivity, configure HSRP priorities and preemption, test failover behavior, and observe how the virtual IP (VIP) and virtual MAC address behave during router failures and recovery.

---

## Topoogy For Reference

<img width="624" height="284" alt="toplogy" src="https://github.com/user-attachments/assets/2cadcd0b-d4ae-43b1-bea6-bdec3c06be95" />

## 🗂️ Tasks

### 🧪 Task 1: Test External Connectivity from PCs
Ping the external server **8.8.8.8** from **PC1** and **PC2**.  
Identify the default gateway currently configured on each PC.

### 🔁 Task 2: Configure HSRPv2 on R1 and R2
Configure **HSRP version 2** on R1 and R2.  
Raise **R1’s priority above the default**, lower **R2’s priority below the default**, and enable **preemption**.

### 🌐 Task 3: Configure VIP as Default Gateway
Configure the **Virtual IP (VIP)** as the default gateway for **PC1** and **PC2**.  
Ping **8.8.8.8** from both PCs and examine the **ARP table** to identify the MAC address mapped to the VIP.

### ⚠️ Task 4: Test HSRP Failover
Power off **R1** (save the configuration first).  
After R1 shuts down, ping **8.8.8.8** from **PC1** and determine whether **R2** is now used as the default gateway.

### 🔄 Task 5: Test HSRP Recovery
Power **R1** back on.  
Observe whether R1 becomes the **active router** again.

---

## ✍️ Author Information
Name: Daysean Mensah <br/>
Course/Program: Cisco CCNA Studies <br/>
Lab completion date: December 15 2025. <br/>
