# 🔀 Task 2 – Configure Router-on-a-Stick (ROAS) for Voice and Data VLANs

## 📌 Objective

Enable **inter-VLAN routing** for:
- 🖥️ **Data VLAN 10** (PCs)
- 📞 **Voice VLAN 20** (IP Phones)

This is done using **Router-on-a-Stick (ROAS)**:

- The **SW1 ↔ R1** link is a **trunk**
- R1 uses **subinterfaces** (one per VLAN) with **802.1Q encapsulation**

## Topology For Reference

<img width="657" height="253" alt="topology" src="https://github.com/user-attachments/assets/3459f83e-c98d-4bca-826a-c8d8641898e7" />

