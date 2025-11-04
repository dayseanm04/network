# 🧩 VLAN, Trunking & Router-on-a-Stick Lab

## 📘 Overview
This lab demonstrates how to configure **VLANs**, **trunk links**, and a **Router-on-a-Stick (ROAS)** setup using Cisco Packet Tracer.  
It simulates inter-VLAN communication through a single physical router interface configured with multiple subinterfaces.

---

## Topology For Reference
<img width="677" height="372" alt="Topolgy" src="https://github.com/user-attachments/assets/8ce31ee8-acef-4cc9-87be-ec91214712e4" />



## 🎯 Objectives
1. Create and assign VLANs on multiple switches.  
2. Configure trunk links between switches.  
3. Set up a Router-on-a-Stick configuration to enable inter-VLAN routing.  
4. Verify connectivity between VLANs.

---

## 🧠 Topology Summary
- **Cisco 2960-24TT Switch(SW1)**: VLAN 10, VLAN 30  
- **Cisco 2960-24TT Switch(SW2)**: VLAN 10, VLAN 20, VLAN 30  
- **Cisco 2911 Router (R1)**: Subinterfaces for VLANs 10, 20, and 30  
- **Trunks**:  
  - `SW1 g0/1 <-> SW2 g0/1`  
  - `SW2 g0/2 <-> R1 g0/0`  
- **Native VLAN:** 100  

---

## 🧰 Tasks Completed
### 🪪 Task 1 – VLAN Configuration
- Created VLAN 10, 20, and 30 on the appropriate switches.  
- Assigned switch ports to their respective VLANs.  
- Verified VLAN creation using `show vlan brief`.

### 🌉 Task 2 – Trunk Configuration
- Configured trunk ports between switches (SW1 ↔ SW2).  
- Allowed VLANs 10 and 30 on SW1 and SW2 trunks.  
- Set native VLAN to 100.  
- Verified trunk operation with `show interface trunk`.

### 🧮 Task 3 – Router-on-a-Stick Configuration
- Configured router subinterfaces for each VLAN  
- Assigned IP addresses (last usable of each subnet) for the subinterface.  
- Enabled routing between VLANs.  
- Verified with `show ip interface brief` and `ping` tests between VLANs.

---

## 📂 Repository Structure
| Folder | Description |
|--------|--------------|
| `configs/` | Contains switch, router, and PC configuration markdown files |
| `pkt-files/` | Packet Tracer files (blank and completed versions) |
| `verification-results.md` | Verification results and screenshots |
| `notes.md` | Reflection and final thoughts |

---

## 🧾 Verification
Successful ping tests confirmed inter-VLAN routing and correct trunk/VLAN configuration.

---

## 🏁 Final Thoughts
The lab emphasized key concepts in:
- VLAN segmentation and trunking  
- Native VLANs  
- Router subinterface configuration for inter-VLAN routing  
- The importance of verifying each step with `show` commands  

---

Use the links below to explore each part of the VLAN Router-On-A-Stick Lab:

| Section | Description |
|----------|--------------|
| 🧩 [**configs/**](./configs) | Contains all device configuration files for SW1, SW2, and R1 (VLANs, trunks, and Router-on-a-Stick setup). |
| 💾 [**pkt-files/**](./pkt-files) | Packet Tracer project files — includes both the **blank** and **completed** versions of the lab. |
| 🖼️ [**topology.png**](./topology.png) | Network diagram showing the switch, router, and PC connections. |
| 🧾 [**verification-results.md**](./verification-results.md) | Contains screenshots and results verifying VLAN creation, trunk setup, and inter-VLAN connectivity. |
| 🧠 [**reflection.md**](./reflection.md) | Personal notes and reflection on what was learned from completing the VLAN ROAS lab. |

---
## ✍️ Author Information

**Name:** *Daysean Mensah*  
**Course/Program:** *Cisco CCNA Studies*  
🧑‍💻 *Created as part of my CCNA studies – documenting network fundamentals.*
