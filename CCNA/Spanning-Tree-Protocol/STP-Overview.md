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
