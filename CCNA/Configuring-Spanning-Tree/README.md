# 🧠 Configuring STP (PVST+)

This lab focuses on understanding and configuring **Spanning Tree Protocol (STP)** using **Per-VLAN Spanning Tree Plus (PVST+)** on Cisco switches. The objective is to verify the STP topology, configure root bridges for different VLANs, manipulate STP parameters like cost and port priority, and enable **PortFast** and **BPDU Guard** for network stability and security.


## Topology For Reference

<img width="454" height="294" alt="Topology" src="https://github.com/user-attachments/assets/72f4a007-e83a-43ed-bb0c-6e4cae158fe3" />

## 🧰 Devices Used
- 4 Cisco 2960-24TT switches
- 2 PCs (PC1 & PC2)  

---

## 🌐 Network Overview

**Switch Connections:**

- SW2 is the **root bridge**.
- SW2 F0/1 → SW4 F0/1  
- SW2 F0/2 → SW3 F0/2  
- SW2 F0/3 → SW1 F0/3  
- SW1 F0/1 → SW3 F0/1  
- SW4 F0/2 → SW1 F0/2

---

## ✅ Tasks Completed

### **🔎 Task 1: Check STP Topology**
- Verified the **current root bridge**.
- Identified **STP port roles and states** for VLANs 1 and 2.

### **🏛️ Task 2: Configure Primary & Secondary Root Bridges**
- I sed SW1 as as the **primary root for VLAN 1** and **secondary for VLAN 2**.  
- I sed SW2 as as the as **primary root for VLAN 2** and **secondary for VLAN 1**.  
- Load balanced for each VLAN

### **⚖️ Task 3: Modify STP Cost**
- Increased cost on SW4 to observe root port selection changes.

### **🔧 Task 4: Change Port Priority**
- Adjusted port priority on SW1 to test tie-breaker behavior.

### **🛡️ Task 5: Enable PortFast & BPDU Guard**
- Enabled PortFast and BPDU Guard on access ports.
- Verified BPDU Guard interface shutdown behavior.

## 🧭 Navigation

Use this section to quickly access all major parts of the **Configuring STP (PVST+)** lab:

### 📂 Main Files
- 📘 [README.md](./README.md) — Overview of the entire PVST+ lab  
- 🖼️ [Topology.png](./Topology.png) — Network topology diagram  
- 📝 [reflection.md](./reflection.md) — Summary, lessons learned, and observations  

### 📁 Task Configurations
All task configuration files are stored in the **task-configs** folder:

- 📂 [task-configs/](./task-configs) - Task configuration files

### 📁 Cisco Packet Tracer files

- 📂 [pkt-files/](./pkt-files) - contains the pkt files for the blank and completed version of the lab

## 📝 Summary

This lab improved my understanding of how PVST+ allows VLAN-specific control, and how modifying STP parameters affects the network topology. I also learned how features like PortFast and BPDU Guard protect the network from misconfigurations and accidental loops.

---

## ✍️ Author Information

**Name:** *Daysean Mensah*  
**Course/Program:** *Cisco CCNA Studies*  
**Lab completion date:** November 10 2025.
