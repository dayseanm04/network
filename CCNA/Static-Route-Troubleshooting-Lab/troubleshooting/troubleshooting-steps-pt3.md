# 🔁 Troubleshooting Steps: Part 3

## 🎯 Objective
In this final part, the goal is to **verify R3’s configuration**, correct its **interface IP address**, and confirm that **PC1 and PC2 can successfully communicate** across the network.  
After fixing R1 and R2, packets reached R3 but stopped there — indicating an IP configuration issue on R3.

---

## Topology For Reference
<img width="683" height="296" alt="TFR" src="https://github.com/user-attachments/assets/110f3bf2-ac22-41dc-9cf9-e90d33c2c55e" />


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

### 🧩 Step 2: Verify R3 Interfaces
- **Command:**  
 ```bash
  show ip int brief
```

**Results**

<img width="813" height="113" alt="R3-interfaces-misconfig" src="https://github.com/user-attachments/assets/c93e40da-e27f-46cc-b685-66c442f8463b" />


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

<img width="817" height="117" alt="R3-interfaces-misconfig" src="https://github.com/user-attachments/assets/a40dcef4-2430-4abb-9462-255d211bce13" />


---

### 🧩 Step 4: Verify R3 Routing Table
- **Commands:**

```bash
show ip route
```

**Results**

<img width="746" height="365" alt="R3-RT" src="https://github.com/user-attachments/assets/4777baaf-9172-4be6-835e-5de8232351df" />



**Observation:**
- 192.168.3.0/24 → directly connected
- 192.168.1.0/24 → static route via R2
- ✅ R3 outing table is  correct.

---

### 🧩 Step 5: Final Ping Test

**Action:** Ping PC2 (192.168.3.1) from PC1 once more in Simulation Mode.

**Simulation**

<img width="684" height="280" alt="Sucess-PC1-R1" src="https://github.com/user-attachments/assets/3e8f03cb-975c-41e8-9dc3-f074864d5cf4" />


- PC1 to SW1 to R1

<img width="685" height="276" alt="Sucess-R1-R2" src="https://github.com/user-attachments/assets/510b26a5-9f3b-45dc-9fd1-f15a6d0a0954" />

- R1 to R2

<img width="685" height="277" alt="Sucess-R2-R3" src="https://github.com/user-attachments/assets/201a8d25-0eec-4c3c-bf06-eccea8f4e2cb" />

- R2 to R3

<img width="689" height="281" alt="Sucess-R3-PC2" src="https://github.com/user-attachments/assets/c002285b-a6fd-4697-be4e-d91a72252e7f" />

- R3 to SW2 to P2

**Observation:**
- PC1 → SW1 → R1 → R2 → R3 → SW2 → PC2

---

PC2 Reply to PC1

**Simulation:**

<img width="683" height="280" alt="PC2-reply1" src="https://github.com/user-attachments/assets/96037aab-7331-4485-b766-ef04b7d9f395" />

- PC2 to SW2 to R3

<img width="679" height="280" alt="PC2-reply2" src="https://github.com/user-attachments/assets/c3f5260d-9a8d-44b5-a1d3-d71d8723a7fd" />

- R3 to R2

<img width="688" height="283" alt="PC2-reply3" src="https://github.com/user-attachments/assets/786524c5-1522-44f7-b486-f84da085eee4" />

- R2 to R1

<img width="706" height="316" alt="PC2-reply4" src="https://github.com/user-attachments/assets/1e8195f8-9af4-4ff4-9a64-53f9d9c8d67f" />

- R1 to SW1 to PC1


**PC2 reply to PC1**

<img width="683" height="280" alt="PC2-reply1" src="https://github.com/user-attachments/assets/96037aab-7331-4485-b766-ef04b7d9f395" />

- PC2 to SW2 to R3

<img width="679" height="280" alt="PC2-reply2" src="https://github.com/user-attachments/assets/c3f5260d-9a8d-44b5-a1d3-d71d8723a7fd" />

- R3 to R2

<img width="688" height="283" alt="PC2-reply3" src="https://github.com/user-attachments/assets/786524c5-1522-44f7-b486-f84da085eee4" />

- R2 to R1

<img width="706" height="316" alt="PC2-reply4" src="https://github.com/user-attachments/assets/1e8195f8-9af4-4ff4-9a64-53f9d9c8d67f" />

- R1 to SW1 to PC1

**Observation:**
- PC2 → SW2 → R3 → R2 → R1 → SW1 → PC1

✅ Ping successful in both directions.
