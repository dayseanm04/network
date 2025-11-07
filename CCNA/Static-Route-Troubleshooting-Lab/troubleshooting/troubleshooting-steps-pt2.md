# 🔁 Troubleshooting Steps: Part 2

## 🎯 Objective
In this section, the goal is to **identify and fix the routing loop** occurring between **R1** and **R2** after the first static route correction on R1.  
The loop prevented packets from reaching R3, beacause the traffic was bouncing repeatedly between R1 and R2.

---

## Topology For Reference
<img width="683" height="296" alt="TFR" src="https://github.com/user-attachments/assets/6dd5a050-a56b-45ce-99c1-091a04d44750" />


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

## 🧠 Step-by-Step Troubleshooting

### 🧩 Step 1: Observe the Loop in Simulation Mode
- **Action:** Ping **PC2 (192.168.3.1)** from **PC1** in **Simulation Mode**.  
- **Observation:**

**Simulation Mode**

<img width="789" height="291" alt="PC1-R1-sim" src="https://github.com/user-attachments/assets/c0177363-cacf-43bb-9b6c-7d1536eaedb5" />

- **The ICMP ping packet it sent to R1**

<img width="739" height="285" alt="R1-R2-Loop" src="https://github.com/user-attachments/assets/10d8ac9e-f9ed-48fa-85e1-36532fd7410e" />

- **R1 forwards the packet to R2**

<img width="693" height="285" alt="R2-R1-Loop" src="https://github.com/user-attachments/assets/8b7391f4-b90b-4a22-b990-db0e4be54ac7" />

- **R2 sends the packet back to 1**
- **And the cycle repeats (LOOP**)

  - Packet travels **PC1 → SW1 → R1 → R2 → R1 → R2** repeatedly.  
  - ❌ This Indicates a **routing loop** between R1 and R2.  
  - This means R2 is sending the packet back toward R1 instead of forwarding it to R3.

---

### 🧩 Step 2: Verify R2 Interfaces IP Addresses
- **Command:**  
```bash
show ip int brief
```

**Expected output✅:**
<img width="818" height="159" alt="R2-interfsces" src="https://github.com/user-attachments/assets/e909da92-b7d8-4156-83c4-544c3bb49b47" />

- ✅ Both interfaces are correctly configured and active.

---

### 🧩 Step 3: Check R2 Routing Table
```bash
show ip route
```
**Results**
<img width="807" height="348" alt="R2-misconfiged-route" src="https://github.com/user-attachments/assets/a389c280-3826-4301-8a31-6c7dceb513be" />

**Observation:**
- Found incorrect static route: the exit interface for packet destined for 192.168.3.0/24 network is g0/0
- ❌ This configuration causes packets destined for 192.168.3.0/24 to be sent via G0/0, sending them back toward R1 and creating a routing loop.
- The correct exit interface for the 192.168.3.0/24 network is G0/1, which points toward R3.

---

### 🧩 Step 4: Correct the Static Route on R2

**Remove the old route and configure new route specify g0/1 as the exit iterfsace for 192.168.3.0/24 network** 

```bash
no ip route 192.168.3.0 255.255.255.0 g0/0
ip route 192.168.3.0 255.255.255.0 g0/1
```

---

### 🧩 Step 5: Verify the Fix

```bash
show ip route
```

**Expected output✅:**
<img width="806" height="354" alt="R2-good-route" src="https://github.com/user-attachments/assets/dbb8c78e-446e-4828-ae31-5a0856259638" />

- The route to 192.168.3.0/24 network point to g0/1
- Routing loop should no longer occur.

---

### 🧩 Step 6: Test the Ping Again

**Observation:**
- Packet now travels PC1 → R1 → R2 and successfully continues toward the next router (R3).
- ✅ Routing loop resolved.


**Continue** [troubleshooting-steps-pt3.md](./troubleshooting-steps-pt3.md)
