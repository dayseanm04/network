# 🧩 Troubleshooting Steps: Part 1

## 🎯 Objective
In this section, the goal is to identify and fix the initial routing issue preventing **PC1** from successfully pinging **PC2**.  
We start from the first ping attempt and continue until the next round of testing after fixing **R1’s static route**.

---

## Topology For Reference

<img width="683" height="296" alt="TFR" src="https://github.com/user-attachments/assets/203c5307-ab6e-4d08-be2e-ed496e23eae7" />

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

### 🧩 Step 1: Verify PC1 IP Configuration
- **Command:** `ipconfig`

**Expected output✅:**
<img width="734" height="371" alt="PC1-ipc" src="https://github.com/user-attachments/assets/c52d735f-5464-40a7-999a-7815730e2ef8" />


**Observation:**  
  - IPv4: `192.168.1.1/24`  
  - Default Gateway: `192.168.1.254`  
- ✅ **PC1 configuration is correct.**

---

### 🧩 Step 2: Ping PC1 default gatway
**Command:** `ping 192.168.1.254`

**Expected output✅:**

<img width="731" height="373" alt="PC1-gateway-ping" src="https://github.com/user-attachments/assets/07e6237e-ed46-4e01-8e6f-0cfb5ef10f9e" />


PC1 can ping its default gateway

---

### 🧩 Step 3: Initial Ping Test
- **Action:** Ping from PC1 → PC2 in **Simulation Mode**.  
- **Observation:**  
  - Packet travels from **PC1 → SW1 → R1**, but does **not** continue past R1.  
  - Indicates a **routing issue** on R1.  

**Simultation Mode:** <br>

<img width="700" height="284" alt="PC1-PC2-Sim" src="https://github.com/user-attachments/assets/06f04827-f433-4895-9d9b-c98b779bd480" />

- The ICMP ping packet was sent from PC1 to SW1 and then to R1, but the packet doesn't get forwarded to R2

---

### 🧩 Step 4: Check R1 Interfaces IP addresses
- **Command:** `show ip int brief`

**Expected output✅:**
<img width="818" height="132" alt="R1-Interfaces" src="https://github.com/user-attachments/assets/2c978243-bdb3-41a5-a4d1-19eeae82eb88" />

- **Observation:**  
  - G0/0 → `192.168.12.1` (up/up)  
  - G0/1 → `192.168.1.254` (up/up)  
- ✅ Both interfaces are correctly configured.

---

### 🧩 Step 5: Verify R1 Routing table
- **Command:**  
```bash
show ip route
```

**Expected output✅:**

<img width="808" height="336" alt="R1-misconfiged-route" src="https://github.com/user-attachments/assets/5f5248f9-1bb3-46a9-b6cf-4fab84d9d1f2" />

- **Observation:**  
- **Found the incorrect route**: The next hop to 192.168.3.0/24 network should be **192.168.12.2** not **192.168.12.3**.

---

### 🧩 Step 6: Fix the Static Route on R1
**First remove the old route and confgure a new route with 192.168.12.2 as the next hop**

- **Commands:**
```bash
no ip route 192.168.3.0 255.255.255.0 192.168.12.3
ip route 192.168.3.0 255.255.255.0 192.168.12.2
```

**Verify with show ip route:**
**Expected output✅:**

<img width="812" height="336" alt="R1-good-route" src="https://github.com/user-attachments/assets/143dee1d-1a0b-4c76-b09e-3f5e844f6527" />

---

### 🧩 Step 7: Ping PC2 again and observe in Simulation Mode.

**Observation:**
-Packet now moves PC1 → SW1 → R1 → R2 → R1 → R2 repeatedly.
-🔁 A Routing loop occurs between R1 and R2.

**Continue** [troubleshooting-steps-pt2.md](./troubleshooting-steps-pt2.md)
