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

---

### More Details below

**📝 Caluclate the Root cost to reach the Root bridge: the total cost of the outgoing interfaces + the path to the root bridge.**

**Note:** Each switch can only have 1 root port

Since **SW3** is the root bridge all of its interface will have a root cost of **0**. so it will advertise the root cost of **0** out of all its interfaces like this. See below: 

<img width="530" height="361" alt="SW3-advertise" src="https://github.com/user-attachments/assets/dec438f3-bb35-4f8f-96e6-aad4f31ef763" />

<br><br>

**SW1 F0/3** and **F0/4** interface will advertise the root cost of 19 to **SW1 F0/1** and **F0/2** interface because its outgoing interfaces are FastEthernet ports with the cost of 19, so 19 + 0 (**SW3 F0/1** and **F0/2** interface cost) is 19. See below:

<img width="510" height="326" alt="SW1-F12-cost" src="https://github.com/user-attachments/assets/788aac69-5a7d-4992-897f-40c86fc18c76" />

<br><br>

**SW2 F0/3** interface will adevertise the root cost of **19** to the Root Bridge **SW3 F0/3** interface, because its outgoing interface is a FastEthernet port with a cost of 19, so 19 + 0 (**SW3 F0/3** interface cost) is 19. See below:

<img width="632" height="347" alt="SW2-F03-cost" src="https://github.com/user-attachments/assets/b475efce-6ddb-4a64-8d53-8d80d38743a4" />

<br><br>

