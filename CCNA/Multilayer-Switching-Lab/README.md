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
- 1 Cisco 3650-24PS switch (SW2)
- 1 Cisco 2960-24TT switch (SW1)  
- 7 PCs (PC1–PC7)  

---

## 🧠 Objectives
- Configure a **point-to-point Layer 3 connection** between R1 and SW2.  
- Enable **IP routing** on the multilayer switch.  
- Configure **Switch Virtual Interfaces (SVIs)** for VLANs.  
- Verify **inter-VLAN communication** and **Internet access**.

---

## ⚙️ Network Setup
- VLAN 10: `10.0.0.0/26` → Last usable IP: `10.0.0.62`  
- VLAN 20: `10.0.0.64/26` → Last usable IP: `10.0.0.126`  
- VLAN 30: `10.0.0.128/26` → Last usable IP: `10.0.0.190`  
- Point-to-Point Link (R1–SW2): `10.0.0.192/30`  
  - R1 G0/0 → `10.0.0.194/30`  
  - SW2 G1/0/2 → `10.0.0.193/30`

---

## 🧩 Tasks Completed

### 🧱 Task 1 – Replace ROAS with Point-to-Point Layer 3 Connection
- Removed all **subinterfaces** on R1.
- Reset R1 g0/0 interface to derfault settings
- Configured **R1 G0/0 interface** with IP `10.0.0.194/30`.  
- Changed **SW2 G1/0/2 interface** to a Layer 3 port and assigned IP `10.0.0.193/30`.  
- Enabled **IP routing** on SW2.  
- Configured a **default route** on SW2 pointing to R1 G0/0.  

---

Configured SVIs on the multilayer switch using the **last usable IP address** of each subnet:
| VLAN | Subnet | SVI IP | Status |
|------|---------|--------|--------|
| 10 | 10.0.0.0/26 | 10.0.0.62 | ✅ Up |
| 20 | 10.0.0.64/26 | 10.0.0.126 | ✅ Up |
| 30 | 10.0.0.128/26 | 10.0.0.190 | ✅ Up |

---

### 🌐 Task 3 – Inter-VLAN Connectivity Test
Ping tests between VLANs confirmed successful communication:

| Source | Destination | Result |
|---------|--------------|---------|
| PC1 (VLAN 10) | PC3 (VLAN 30) | ✅ Success |
| PC1 (VLAN 10) | PC5 (VLAN 20) | ✅ Success |
| PC4 (VLAN 30) | PC6 (VLAN 10) | ✅ Success |
| PC5 (VLAN 20) | PC2 (VLAN 10) | ✅ Success |

---

### 🌍 Task 4 – Internet Connectivity Test
Pinged external IP `1.1.1.1` from multiple PCs:
| Device | Result |
|---------|---------|
| PC1 | ✅ Success |
| PC3 | ✅ Success |
| PC5 | ✅ Success |
| PC7 | ✅ Success |

---

## 🧭 Navigation

📁 **Lab Structure**

| Section | Description |
|----------|--------------|
| 🧩 [Task-Configurations](./Task-Configurations/) | Contains Task 1 and Task 2 configuration steps for the Multilayer Switching Lab. |
| 🌐 [Task3-InterVLAN-Connectivity-Test.md](./Task3-InterVLAN-Connectivity-Test.md) | Verifies inter-VLAN communication between devices. |
| 🌍 [Task4-Internet-Connectivity-Test.md](./Task4-Internet-Connectivity-Test.md) | Verify the Internet connectivity (pby inging 1.1.1.1). |
| 🧠 [Reflection.md](./Reflection.md) | Personal reflection summarizing lessons learned from the lab. |
| 🖼️ [topology.png](./topology.png) | Visual representation of the Multilayer Switching Lab topology. |
| 💾 [pkt-files](./pkt-files/) | Contains blank and completed Packet Tracer files for this lab. |

