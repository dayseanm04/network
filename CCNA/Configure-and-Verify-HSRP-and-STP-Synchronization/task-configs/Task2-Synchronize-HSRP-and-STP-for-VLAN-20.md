# 🔁 Task2 Synchronize HSRP and STP for VLAN 20

## 📌 Objective

Synchronize **HSRP** and **STP** roles for **VLAN 20** so that:
- **DSW2** is the **HSRP Active Gateway** and **STP Root Bridge**
- **DSW1** is the **HSRP Standby Gateway** and **STP Secondary Root**

This alignment ensures hosts in VLAN 20 use the **most direct path** to their default gateway.

## Topology For Reference

<img width="618" height="332" alt="Topology" src="https://github.com/user-attachments/assets/67061080-b132-4e96-a33b-6c05489f583e" />

---

## 📋 VLAN 20 HSRP Configs

| Setting | Value |
|------|------|
| HSRP Version | 2 |
| HSRP Group | 20 |
| Virtual IP (VIP) | 10.0.20.200 |
| DSW2 Priority | 120 |
| DSW1 Priority | 80 |
| Preempt | Enabled |

---
