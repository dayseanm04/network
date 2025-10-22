# 🔁 Troubleshooting Steps: Part 3

## 🎯 Objective
In this final part, the goal is to **verify R3’s configuration**, correct its **interface IP address**, and confirm that **PC1 and PC2 can successfully communicate** across the network.  
After fixing R1 and R2, packets reached R3 but stopped there — indicating an IP configuration issue on R3.

---

## Topology For Reference
<img width="682" height="275" alt="TFR" src="https://github.com/user-attachments/assets/3cc35f18-e8d9-4713-ae2b-0accfc407b19" />

---

## 🖥️ Correct IP Address Information

| Device | Interface | IP Address | Subnet Mask | Description |
|:--------|:-----------|:------------|:-------------|:-------------|
| **PC1** | NIC | 192.168.1.1 | /24 | Host in LAN 1 |
| **PC2** | NIC | 192.168.3.1 | /24 | Host in LAN 2 |
| **R1** | G0/1 | 192.168.1.254 | /24 | LAN 1 Gateway |
| **R1** | G0/0 | 192.168.12.1 | /24 | Link to R2 |
| **R2** | G0/0 | 192.168.12.2 | /24 | Link to R1 |
| **R2** | G0/1 | 192.168.13.2 | /24 | Link to R3 |
| **R3** | G0/0 | 192.168.13.3 | /24 | Link to R2 |
| **R3** | G0/1 | 192.168.3.254 | /24 | LAN 2 Gateway |

---

## 🧠 Step-by-Step Troubleshooting

### 🧩 Step 1: Observe Packet Flow in Simulation Mode
- **Action:** Ping **PC2 (192.168.3.1)** from **PC1** again in **Simulation Mode**.  
- **Observation:**  
  - Packet moves **PC1 → SW1 → R1 → R2 → R3** but stops at **R3**.  
  - ❌ ICMP request does not reach PC2.  

--- 

---

### 🧩 Step 2: Verify R3 Interfaces
- **Command:**  
 ```bash
  show ip int brief
```

**Results**
<img width="813" height="114" alt="R3-interfaces-misconfig" src="https://github.com/user-attachments/assets/a4280293-f7f3-4e49-bbbe-3806d0f1112f" />

- g0/0 ip address is incorrect
- it should be 192.168.13.3/24, not 192.168.23.2/24.

---

### 🧩 Step 3: Fix the Interface IP on R3
**On R3 enter interface g0/0 config mode**
- **Commands:**
```bash
ip address 192.168.13.3 255.255.255.0
```

**Verify configuration:**

```bash
show ip int brief
```

**Expected output✅:**
<img width="807" height="108" alt="R3-interfaces-fixed" src="https://github.com/user-attachments/assets/26178789-ea6d-41a5-8bfb-4b591cda1117" />

---

### 🧩 Step 4: Verify R3 Routing Table
- **Commands:**

```bash
show ip route
```

**Results**

<img width="743" height="362" alt="R3-RT" src="https://github.com/user-attachments/assets/99c2e7e7-7d7e-402b-ab7b-ef2f5caef886" />


**Observation:**
- 192.168.3.0/24 → directly connected
- 192.168.1.0/24 → static route via R2
- ✅ R3 outing table is  correct.

---
