# 🔁 Troubleshooting Steps: Part 2

## 🎯 Objective
In this section, the goal is to **identify and fix the routing loop** occurring between **R1** and **R2** after the first static route correction on R1.  
The loop prevented packets from reaching R3, beacause the traffic was bouncing repeatedly between R1 and R2.

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
