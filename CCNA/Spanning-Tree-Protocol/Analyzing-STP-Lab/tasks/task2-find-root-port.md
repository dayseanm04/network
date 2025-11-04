# ⚙️ Task 2: Identify the Root Port

## 🎯 Objective
This task, is to determined the **root port** on each non-root switch. **Note:** Each switch can only have 1 root port

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

🔗 **[Click here to view how to calculate the root cost →](./task2-calculate-root-cost.md)**

---

## 🧭 Step 2: Root Port Selection

Each non-root switch must choose **one Root Port (RP)**, the port with the **lowest total cost** to reach the Root Bridge.

If multiple ports have the same root cost, STP uses **tie-breakers**:
1. Lowest **Neighbor Bridge ID**
2. Lowest **Neighbor Port ID**

---

## 🧱 SW1 (Non-Root)

<img width="510" height="326" alt="SW1-F12-cost" src="https://github.com/user-attachments/assets/740bd238-20c5-4163-9fed-294ae0a2293f" />

- There are two possible paths to SW3 (via F0/3 and F0/4)
- Both have **equal root cost = 19**
- **SW3** is the neighbor in this case so to break the tie, Check **SW3 port ID**

### On SW3 in Priviliged EXEC mode:

```bash
show spanning-tree
```

**Expected output: ✅**

<img width="529" height="153" alt="SW3-show-stp" src="https://github.com/user-attachments/assets/c806d59f-4e38-4f8d-9e78-581d283338c8" />

### STP port ID = the port priority + the port number
- SW3 F0/1 → Port ID = 128 + 1 = 129
- SW3 F0/2 → Port ID = 128 + 2 = 130

### ✅ SW1 Root Port = F0/4 (connected to the lowest Port ID on SW3)

---

### 🧱 SW2 (Non-Root)
- Receives advertisements:
  - From SW1 F0/1 & F0/2 → Cost = 19 ( + the path to reach SW3 F0/1 & F0/2 interfaces = 19 + 19 = 32)
  - From SW3 F0/3 → Cost = 19
  - From SW4 G0/1 → Cost = 8

### ✅ **SW2 Root Port = G0/1** (lowest total cost path to the Root = 8)

### On SW2 in Priviliged EXEC mode:

```bash
show spanning-tree
```

**Expected output: ✅**

<img width="534" height="148" alt="SW2-show-stp" src="https://github.com/user-attachments/assets/94dbc20a-0351-47e4-be94-4d4e6847d553" />

---

### 🧱 SW4 (Non-Root)
- Advertised cost = 0 on G0/2
- Interface cost (G0/2) = 4
- Total = **4**

### ✅ **SW4 Root Port = G0/2**

### On SW4 in Priviliged EXEC mode:

```bash
show spanning-tree
```

**Expected output: ✅**

<img width="545" height="112" alt="SW4-show-stp" src="https://github.com/user-attachments/assets/720c28de-eae9-476e-b4e0-14e9768a0259" />

## Topology For Rerference
<img width="632" height="347" alt="RootPorts" src="https://github.com/user-attachments/assets/b15d6e65-e503-411e-863f-d6b6a7944560" />


