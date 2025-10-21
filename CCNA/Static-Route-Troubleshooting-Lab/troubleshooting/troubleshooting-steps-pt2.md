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

---
