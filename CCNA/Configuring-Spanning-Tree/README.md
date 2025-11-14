# 🧠 Configuring STP (PVST+)

This lab focuses on understanding and configuring **Spanning Tree Protocol (STP)** using **Per-VLAN Spanning Tree Plus (PVST+)** on Cisco switches. The objective is to verify the STP topology, configure root bridges for different VLANs, manipulate STP parameters like cost and port priority, and enable **PortFast** and **BPDU Guard** for network stability and security.


## Topology For Reference

<img width="454" height="294" alt="Topology" src="https://github.com/user-attachments/assets/72f4a007-e83a-43ed-bb0c-6e4cae158fe3" />

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
