# 🔁 Task1 Synchronize HSRP and STP for VLAN 10

## 📌 Objective

Synchronize **HSRP** and **STP** roles for **VLAN 10** so that:
- **DSW1** is the **HSRP Active Gateway** and **STP Root Bridge**
- **DSW2** is the **HSRP Standby Gateway** and **STP Secondary Root**

This alignment ensures hosts in VLAN 10 use the **most direct path** to their default gateway.

---

## 🧠 Simple Explanation
- **STP** controls the Layer 2 path to the root bridge
- **HSRP** controls the Layer 3 default gateway
- When the **HSRP Active = STP Root**, traffic flows efficiently

## Topology For Reference

<img width="618" height="332" alt="Topology" src="https://github.com/user-attachments/assets/67061080-b132-4e96-a33b-6c05489f583e" />

