# 🧠 Analyzing Spanning Tree Protocol (STP) Lab

## Topology For Reference
<img width="758" height="349" alt="Topology" src="https://github.com/user-attachments/assets/6e395411-796c-4456-86e3-87b9cc7f3e44" />


## 📘 Overview
This lab focuses on **analyzing the operation of the Spanning Tree Protocol (STP)** within a switched network topology. STP prevents switching loops and ensures a single active path between switches by electing a **Root Bridge** and placing redundant links into a **blocking** state.

Through this lab, I determined which switch became the **Root Bridge**, identified the **Root Port, Designated and Non Designated ports** of each switch, and analyzed **root path costs** between switches.

---

## 🧩 Tasks Completed
### 🧱 **Task 1: Identifed the Root Bridge**
- Compared switch priorities and MAC addresses:  
- ✅ **Result:** **SW3** is the **Root Bridge** because it has the lowest bridge priority value.  

---

### 🔍 **Task 2: Determined the Root Port, Designated and Non Designated ports** of each switch
| **Speed** | **Port Cost** |
|------------|---------------|
| FastEthernet (100 Mbps) | 19 |
| GigabitEthernet (1 Gbps) | 4 |
