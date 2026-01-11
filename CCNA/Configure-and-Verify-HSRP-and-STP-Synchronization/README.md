# 🔁 Configure and Verify HSRP and STP Synchronization

## 📌 Summary

This lab focuses on **synchronizing HSRP and Spanning Tree Protocol (STP)**.  
The goal is to ensure that the **HSRP active gateway is also the STP root bridge** for each VLAN.

When HSRP and STP are aligned, traffic from end hosts follows the **most direct and efficient path** to the default gateway, improving performance and avoiding unnecessary Layer 2 detours.

## 🎯 Lab Objectives

By completing this lab, you will be able to:
- Configure **HSRP** on distribution switches (DSW1 and DSW2)
- Control **STP root bridge placement per VLAN**
- Synchronize **Layer 2 (STP)** and **Layer 3 (HSRP)** roles
- Design a more **efficient** network

## Topology For Reference

<img width="618" height="332" alt="Topology" src="https://github.com/user-attachments/assets/67061080-b132-4e96-a33b-6c05489f583e" />

---



