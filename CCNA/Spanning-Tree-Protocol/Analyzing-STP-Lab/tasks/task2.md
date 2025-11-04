# ⚙️ Task 2: Identify the Role of Each Switch Port

## 🎯 Objective
This task, is determined the **role of each switch port** (Root Port, Designated Port, or Non-Designated Port) and calculate the **root path cost** to reach the **Root Bridge (SW3)**.

I also have to identify which ports are **forwarding** and which are **blocking**, based on the STP rules.

---

## 🌐 Network Connection Overview

### 🔌 Switch Interconnections

| **Connection** | **Description** |
|-----------------|----------------|
| SW1 F0/1 ↔ SW2 F0/1 | FastEthernet link |
| SW1 F0/2 ↔ SW2 F0/2 | FastEthernet link |
| SW1 F0/3 ↔ SW3 F0/2 | FastEthernet link |
| SW1 F0/4 ↔ SW3 F0/1 | FastEthernet link |
| SW2 F0/3 ↔ SW3 F0/3 | FastEthernet link |
| SW2 G0/1 ↔ SW4 G0/1 | GigabitEthernet link |
| SW3 G0/1 ↔ SW4 G0/2 | GigabitEthernet link |


<img width="566" height="336" alt="SW-Connections" src="https://github.com/user-attachments/assets/2e2055bf-691e-4527-b2f2-cc545531bee4" />

---

## ⚡ STP Port Cost Reference

| **Interface Speed** | **STP Cost** |
|----------------------|--------------|
| FastEthernet (100 Mbps) | 19 |
| GigabitEthernet (1 Gbps) | 4 |

STP uses these costs to decide which path to the Root Bridge is the best (lowest cost).

---

## 🧮 Step 1: Determine Root Path Costs

Each switch calculates its **total cost** to reach the Root Bridge (SW3).  
The Root Bridge itself has a cost of **0**.



**📝 Caluclate the root cost: (the total cost of the outgoing interface + the path to the root bridge = the total cost).**


### Summary

| **Switch** | **Interface** | **Advertised Cost** | **Interface Cost** | **Total Root Cost** | **Notes** |
|-------------|----------------|--------------------|--------------------|--------------------|-----------|
| **SW3** | All Ports | 0 | 0 | 0 | Root Bridge |
| **SW1 F0/3 & F0/4** | Connected to SW3 | 0 | 19 | **19** | Two equal-cost paths |
| **SW2 F0/3** | Connected to SW3 | 0 | 19 | **19** | Direct link |
| **SW4 G0/2** | Connected to SW3 | 0 | 4 | **4** | Lowest cost path |
| **SW2 G0/1** | Connected to SW4 | 4 | 4 | **8** | Via SW4 |

🔗 **[Click here to view how to calculate the root cost →](./calculate-root-cost.md)**

---
