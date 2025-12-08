# 🛰️ Configuring OSPF Lab – Part 1

This lab focuses on building an OSPF network using four routers. I will configure OSPF on the routers, loopback interfaces, passive interfaces, I also configure a default route on R1. The goal is to understand how OSPF neighbors form, how networks are advertised, and how default routes propagate through the OSPF domain. 

---

## Topology For Reference

<img width="711" height="341" alt="Topology" src="https://github.com/user-attachments/assets/d89ca45d-f7db-403a-bce5-50022fe25b64" />

## ✅ Tasks Completed

### **📝 Task 1: Configure Hostnames & IP Addresses**
- Assigned hostnames to R1–R4.
- Configured interface IP addresses.
- Enabled router interfaces using `no shutdown`.
- (ISPR1 not required for this lab).
- Verified using `show ip interface brief`.

---

### **🔁 Task 2: Configure Loopback Interfaces**
- Added Loopback0 to each router:
  - R1 → 1.1.1.1/32  
  - R2 → 2.2.2.2/32  
  - R3 → 3.3.3.3/32  
  - R4 → 4.4.4.4/32  
- Verified using `show ip interface brief`.

---

### **🌐 Task 3: Configure OSPF on All Routers**
- Enabled OSPF **process 1**.
- Enabled OSPF on the required interfaces with the network command (excluding R1’s Internet-facing interface).  
- Enabled OSPF on loopbacks.  
- Configured loopback interfaces as **passive**.  
- configured passive interfaces where appropriate (including R4's LAN).

---

### **🚦 Task 4: Configure R1 as an ASBR**
- R1 was configured as an **Autonomous System Boundary Router**.
- Used `default-information originate` to inject a default route into OSPF.
- Added a static default route on R1 pointing toward the ISP (`ip route 0.0.0.0 0.0.0.0 203.0.113.2`).  
- Verified that R1 now shows a default route and is identified as an ASBR.

---

### **🔍 Task 5: Verify Default Route on R2, R3, and R4**
- Checked routing tables on R2, R3, and R4 using `show ip route`.
- Confirmed that each router received an **O*E2** default route.
- Verified that the default route appears only after I configured R1 default route.

## 📚 Navigation

Use this section to navigate through the OSPF Lab Part 1 files:

| Section | Link |
|--------|------|
| 🧪 **Task Configurations (Step-by-Step Guides)** | [task-configs/](task-configs/) |
| 🖼️ **Topology Diagram** | [Topology.png](Topology.png) |
| 📁 **Packet Tracer Files (Blank & Completed)** | [pkt-files/](pkt-files/) |
| 💭 **Reflection** | [reflection.md](reflection.md) |

---

### ✍️ Author Information
Name: Daysean Mensah <br/>
Course/Program: Cisco CCNA Studies <br/>
Lab completion date: Dec 07 2025. <br/>
