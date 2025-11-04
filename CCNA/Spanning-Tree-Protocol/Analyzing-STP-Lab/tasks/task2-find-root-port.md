# ⚙️ Task 2: Identify the Root Port

## 🎯 Objective
This task, is to determined the **root port** on each non-root switch.

---

## 🌐 Network Connection Overview


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
| **SW1 F0/3 & F0/4** | Connected to SW3 | 0 | 19 | **19** | Two equal path cost |
| **SW2 F0/3** | Connected to SW3 | 0 | 19 | **19** | Direct link |
| **SW4 G0/2** | Connected to SW3 | 0 | 4 | **4** | Lowest cost path |
| **SW2 G0/1** | Connected to SW4 | 4 | 4 | **8** | Via SW4 |

🔗 **[Click here to view how to calculate the root cost →](./calculate-root-cost.md)**

---

## 🧭 Step 2: Root Port Selection

Each non-root switch must choose **one Root Port (RP)**, the port with the **lowest total cost** to reach the Root Bridge.

If multiple ports have the same root cost, STP uses **tie-breakers**:
