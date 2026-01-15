# 🛠️ Task 1 Configure IP Addressing  and Routing for Full Connectivity

## 📌 Objective

Configure **IP addressing** on all devices and configure **static routing** on the routers so the network has **full end-to-end connectivity**.

This step is required before attempting any **TFTP or FTP file transfers**.

---

## 🧠 Simple Explanation
- All devices must have correct **IP addresses**
- Routers must know how to reach **remote networks**
- File transfers (TFTP/FTP) will **fail** if connectivity is not working

## Topology For Reference

<img width="545" height="196" alt="topology" src="https://github.com/user-attachments/assets/1895f9fd-c6d2-42f5-ba47-2e54b059671f" />

---

## 🌐 Addressing Overview


| Device | Interface | IP Address | Subnet Mask |
|------|----------|------------|-------------|
| R1 | G0/1 | 10.0.0.254 | 255.255.255.0 |
| R1 | G0/0 | 192.168.12.1 | 255.255.255.252 |
| R2 | G0/0 | 192.168.12.2 | 255.255.255.252 |
| SRV1 | NIC | 10.0.0.1 | 255.255.255.0 |


---
