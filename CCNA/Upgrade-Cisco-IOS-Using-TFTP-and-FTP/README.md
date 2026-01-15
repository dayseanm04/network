# 🔄 Upgrade Cisco IOS Using TFTP and FTP

## 📌 Summary

This lab focuses on upgrading **Cisco router IOS images** using two common file transfer protocols:
- **TFTP** (Trivial File Transfer Protocol)
- **FTP** (File Transfer Protocol)

I will configure IP addresses for the interfaces, static routes, transfer IOS images from a server, upgrade router operating systems, and deleted old files from flash memory.

## Topology For Reference

<img width="545" height="196" alt="topology" src="https://github.com/user-attachments/assets/1895f9fd-c6d2-42f5-ba47-2e54b059671f" />

---

## 🎯 Lab Objectives

By completing this lab, you will be able to:
- Configure IP addressing and routing for full network connectivity
- Transfer IOS images using **TFTP** and **FTP**
- Upgrade router IOS software
- Manage router flash memory by removing old IOS images
- Verify successful IOS upgrades

---

## 🧪 Lab Tasks Overview

### 🛠️ Task 1 – Configure IP Addressing and Routing

- Assign IP addresses to all devices
- Configure routing on routers to ensure full network connectivity

📌 *Purpose:* Ensure all devices can communicate before attempting file transfers.

---

### 📤 Task 2 – Transfer IOS Image to R1 Using TFTP

- Use **TFTP** on **R1** to download the IOS image from **SRV1**
- File: `c2900-universalk9-mz.SPA.155-3.M4a.bin`

📌 *Purpose:* Practice IOS file transfers using TFTP.

---

### 🔄 Task 3 – Upgrade R1 IOS and Clean Up Flash

- Set the new IOS image as the boot image
- Reload the router
- Delete the old IOS file from flash memory

📌 *Purpose:* Complete the IOS upgrade process on R1.

---




## ✍️ Author Information

**Name:** *Daysean Mensah*  
**Course/Program:** *Cisco CCNA Studies*  
**Lab completion date:** january 12 2026.
