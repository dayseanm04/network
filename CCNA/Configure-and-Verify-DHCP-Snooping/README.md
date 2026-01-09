# 🛡️ Configure and Verify DHCP Snooping

## 📌 Summary

This lab focuses on **securing DHCP operations using DHCP Snooping**.  
DHCP Snooping helps protect the network from **rogue DHCP servers** by controlling which switch ports are allowed to send DHCP server messages.

In this lab, I configured R1 as a **legitimate DHCP server**, i enabled DHCP Snooping on switches, and I test client behavior to observe how **trusted and untrusted ports** affect DHCP traffic.

## Topology For Reference

<img width="667" height="221" alt="topology" src="https://github.com/user-attachments/assets/0437e21d-9c1c-483d-b25a-dc0aa1e8f15a" />

---

## 🎯 Lab Objectives

By completing this lab, you will be able to:
- Configure a router as a **DHCP server**
- Enable **DHCP Snooping** on Layer 2 switches
- Identify **trusted vs untrusted interfaces**
- Observe DHCP failures caused by **DHCP Snooping Option 82**
- Apply the correct fix to restore DHCP functionality

---

## 🧪 Lab Tasks Overview
