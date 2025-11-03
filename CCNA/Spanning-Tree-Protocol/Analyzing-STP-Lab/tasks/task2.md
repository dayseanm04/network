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


<img width="566" height="356" alt="SW-Connections" src="https://github.com/user-attachments/assets/2e2055bf-691e-4527-b2f2-cc545531bee4" />

---

