# ⚙️ VLAN Router-On-A-Stick Lab Configurations

This folder contains all of the **device configuration files** used in the **VLAN Router-On-A-Stick Lab**.  
Each file corresponds to a specific **lab task** and **network device**.

---

These files can be used to:
- Re-create this lab in Cisco Packet Tracer  
- Review configuration steps for each task  
- Troubleshoot or compare results during verification  

---

## 📄 File Descriptions

| File | Description |
|------|--------------|
| **task-1-sw1-config.md** | Configuration steps for **Switch 1 (SW1)**  VLAN 10 & VLAN 30 setup |
| **task-1-sw2-config.md** | Configuration steps for **Switch 2 (SW2)**  VLAN 10 & VLAN 20 setup |
| **task-2-sw1-to-sw2-trunk-config.md** | Trunk configuration between **SW1 ↔ SW2**, allowing VLANs 10 and 30 with native VLAN 100 |
| **task-3-router-on-a-stick-config.md** | Router-on-a-Stick setup: **SW2 trunk to R1**, subinterfaces for VLANs 10, 20, and 30 |

---

## 🧩 Tasks

| Task | Description |
|------|--------------|
| **Task 1** | VLAN creation and port assignments on both switches |
| **Task 2** | Trunk configuration between switches |
| **Task 3** | Router-on-a-Stick configuration for inter-VLAN routing |

---

## 🧠 Notes
- Each configuration file includes both the **commands** and **verification steps**.  
- Save configurations after each step using:  
  ```bash
  write memory
