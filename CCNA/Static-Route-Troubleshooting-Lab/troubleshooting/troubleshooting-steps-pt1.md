# 🧩 Troubleshooting Steps: Part 1

## 🎯 Objective
In this section, the goal is to identify and fix the initial routing issue preventing **PC1** from successfully pinging **PC2**.  
We start from the first ping attempt and continue until the next round of testing after fixing **R1’s static route**.

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

### 🧩 Step 1: Verify PC1 IP Configuration
- **Command:** `ipconfig`

**Expected output✅:**
<img width="739" height="370" alt="PC1-ipc" src="https://github.com/user-attachments/assets/ff18a3b3-8ffc-413f-bc35-6459a98646f3" />

**Observation:**  
  - IPv4: `192.168.1.1/24`  
  - Default Gateway: `192.168.1.254`  
- ✅ **PC1 configuration is correct.**

---

### 🧩 Step 2: Ping PC1 default gatway
**Command:** `ping 192.168.1.254`

**Expected output✅:**
<img width="737" height="376" alt="PC1-gateway-ping" src="https://github.com/user-attachments/assets/edee99c1-c304-465c-b1a7-ea5645ba23ae" />


PC1 can ping its default gateway

---

### 🧩 Step 3: Initial Ping Test
- **Action:** Ping from PC1 → PC2 in **Simulation Mode**.  
- **Observation:**  
  - Packet travels from **PC1 → SW1 → R1**, but does **not** continue past R1.  
  - Indicates a **routing issue** on R1.  

**Simultation Mode:** <br>
<img width="695" height="279" alt="PC1-PC2-Sim" src="https://github.com/user-attachments/assets/c968a3a7-202e-4940-8678-c3180a6f2414" />
- The ICMP ping packet was sent from PC1 to SW1 and then to R1, but the packet doesn't get forwarded to R2

---

### 🧩 Step 4: Check R1 Interfaces IP addresses
- **Command:** `show ip int brief`

**Expected output✅:**
<img width="814" height="128" alt="R1-Interfaces" src="https://github.com/user-attachments/assets/c5101978-ad25-44f0-b8ce-541735511972" />

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
<img width="805" height="332" alt="R1-misconfiged-route" src="https://github.com/user-attachments/assets/49a654d9-fb4d-461b-98dd-f1db76a40289" />


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
<img width="810" height="333" alt="R1-good-route" src="https://github.com/user-attachments/assets/a7844f1f-439d-485b-b653-13417d02d86c" />

---

### 🧩 Step 7: Ping PC2 again and observe in Simulation Mode.

Observation: Packet now moves PC1 → SW1 → R1 → R2 → R1 → R2 repeatedly.
🔁 A Routing loop occurs between R1 and R2.

**Continue** [troubleshooting-steps-pt2.md](./troubleshooting-steps-pt2.md)
