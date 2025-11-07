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

<img width="794" height="296" alt="PC1-R1-sim" src="https://github.com/user-attachments/assets/da6a8882-7397-417e-a4b6-eb7c0e4143e6" />


- **The ICMP ping packet it sent to R1**

<img width="743" height="289" alt="R1-R2-Loop" src="https://github.com/user-attachments/assets/d5d17862-9787-420a-b049-9b36345c8d6a" />


- **R1 forwards the packet to R2**

<img width="696" height="291" alt="R2-R1-Loop" src="https://github.com/user-attachments/assets/b9a43cc7-e347-43e5-ac28-2ce77bb4f7df" />


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
<img width="820" height="163" alt="R2-int" src="https://github.com/user-attachments/assets/6b1e4781-d306-49a5-84d3-d50d9d7f569c" />


- ✅ Both interfaces are correctly configured and active.

---

### 🧩 Step 3: Check R2 Routing Table
```bash
show ip route
```

**Results**

<img width="810" height="353" alt="R2-misconfiged-route" src="https://github.com/user-attachments/assets/818573be-24c3-416c-9278-79c97c68b780" />


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

<img width="810" height="361" alt="R2-good-route" src="https://github.com/user-attachments/assets/6491fe0e-b55d-404a-bd93-348304906ba6" />

- The route to 192.168.3.0/24 network point to g0/1
- Routing loop should no longer occur.

---

### 🧩 Step 6: Test the Ping Again

**Observation:**
- Packet now travels PC1 → R1 → R2 and successfully continues toward the next router (R3).
- ✅ Routing loop resolved.


**Continue** [troubleshooting-steps-pt3.md](./troubleshooting-steps-pt3.md)
