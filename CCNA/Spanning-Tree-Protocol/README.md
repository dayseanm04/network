# 🕸️ Spanning Tree Protocol (STP)

## Overview
**Spanning Tree Protocol (STP)** is a Layer 2 network protocol designed to **prevent loops** in networks with redundant connections. It ensures that there is only **one active path** between two network devices at any time.

STP is standardized as **IEEE 802.1D**. Without it, switches can end up sending the same endless broadcast frames creating what’s called a **broadcast storm**, which can crash the network.

STP helps maintain a **loop-free logical topology** while still allowing **physical redundancy** for backup connections.

---

## 🌀 What Happens Without STP (Broadcast Storms)

### Topology For Reference:

<img width="472" height="290" alt="Screenshot 2025-11-01 230843" src="https://github.com/user-attachments/assets/fb5f48f9-33ac-432e-a2b8-e9cb7d261135" />


If **Switch1** sends a broadcast frame, it gets forwarded to **Switch2** and **Switch3**. So **Switch2** forwards the frame to **Switch3**.
**Switch3** forwards the frame to **Switch2**. **Switch3** will then forward the frame to **Switch1** and also **Switch2** will then forward the frame to **Switch1**.

**Note: Broadcast frames is sent out of every interface execept the interfeace it reciefed the broacast frame from**


**STP prevents this** by automatically placing one or more ports into a **blocking state**, breaking the loop while keeping backup links ready if the main path fails.

---

## 🌳 How STP Works
STP uses the **Spanning Tree Algorithm (STA)** to decide which ports will forward traffic and which will block. It relies on special messages called **Bridge Protocol Data Units (BPDU)** to share information between switches.

Here’s the general process:
1. **Root Bridge Election:** The switches exchange BPDUs to choose a single **Root Bridge (Root Switch)**.  
   - The Root Bridge is chosen based on the lowest **Bridge ID (BID)**.
   - The BID is made up of:
     - A **priority value** (default: 32768)
     - The **MAC address** of the switch  
     - If all switches have the same priority, the one with the lowest MAC address becomes the Root Bridge.

### 🔹 How to Change Bridge Priority
You can change a switch’s priority to influence the Root Bridge election.  
A lower value means **higher priority**.

To manually set the bridge priority:

```bash
Switch(config)# spanning-tree vlan 1 priority 24576
```

**Note:** ⚠️ The priority value must be in increments of 4096. So: 0, 4096, 8192, 12288, 16384, 20480, 24576, 28672, 32768, 36864, 40960, 45056, 49152, 53248, 57344, 61440

<br/>

2. **Port Roles**
   - **Root Ports (RP):**  Ports with the **lowest cost path** to the Root Bridge (forwarding state).
   - **Designated Ports (DP):**  Ports that forward traffic **away** from the Root Bridge (forwarding state).
   - **Blocked Ports(BP):**  Ports that **do not forward frames**, preventing loops.

3. **Path Cost Calculation**
   - STP calculates the best path to the Root Bridge based on **path cost**, which depends on link speed:

     | Speed | Cost |
     |--------|------|
     | 10 Mbps | 100 |
     | 100 Mbps | 19 |
     | 1 Gbps | 4 |
     | 10 Gbps | 2 |

You can manually change a port’s cost with:
```bash
spanning-tree cost VALUE
```
---

## ⚙️ Bridge Protocol Data Unit (BPDU)
**BPDUs** messages used by switches send to share STP information with each other switches.  
Each BPDU contains:
- Root Bridge ID  
- Sender’s Bridge ID  
- Sender’s path cost to the root  

BPDUs are used to:
- Elect the **Root Bridge**
- Detect loops

---

## 🏛️ Root Bridge Election and Optimization
By default, every switch has a **Bridge Priority** of **32768**. If you don’t manually configure it, the switch with the **lowest MAC address** becomes the Root Bridge.

This can lead to **poor performance because older switches often have lower MAC addresses and slower hardware**.  
To avoid that, you can **manually set the root bridge** using these commands:

## Set a switch as the primary root bridge

```bash
Switch1(config)# spanning-tree vlan 1 root primary
```

## Set another switch as the secondary root bridge (backup)

```bash
Switch2(config)# spanning-tree vlan 1 root secondary
```

**Note:** 
- The primary root has a lower priority (24576).
- The secondary root has a slightly higher priority (28672).
- If the primary fails, the secondary automatically takes over


