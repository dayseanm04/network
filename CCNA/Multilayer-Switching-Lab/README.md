# 🧩 Multilayer Switching Lab

## 📘 Overview
This lab focuses on configuring **inter-VLAN routing using a multilayer switch** instead of the Router-on-a-Stick (ROAS) configuration. It builds on the previous **VLAN-Router-on-a-Stick Lab** configuration, replacing the router subinterfaces with a **Layer 3 point-to-point connection** between **R1** and **SW2**.  

By the end of this lab, the network will have **full inter-VLAN connectivity** and **Internet access** through the Multilayer Switch.

---

## Topology For Reference
<img width="672" height="333" alt="topology" src="https://github.com/user-attachments/assets/a184dcd7-a2a7-450e-b700-8637ccfe82b7" />

---

## 🧰 Devices Used
- 1 Cisco 2911 Router (R1)  
- 1 Cisco 3650-24PS (SW2)
- 1 Cisco 2960-24TT (SW1)  
- 7 PCs (PC1–PC7)  

---

## 🧠 Objectives
- Configure a **point-to-point Layer 3 connection** between R1 and SW2.  
- Enable **IP routing** on the multilayer switch.  
- Configure **Switch Virtual Interfaces (SVIs)** for VLANs.  
- Verify **inter-VLAN communication** and **Internet access**.

---
