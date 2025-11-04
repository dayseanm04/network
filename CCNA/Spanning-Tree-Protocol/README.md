# 🕸️ Spanning Tree Protocol (STP)

## Overview
**Spanning Tree Protocol (STP)** is a Layer 2 network protocol designed to **prevent loops** in networks with redundant connections. It ensures that there is only **one active path** between two network devices at any time.

STP is standardized as **IEEE 802.1D**. Without it, switches can end up sending the same endless broadcast frames creating what’s called a **broadcast storm**, which can crash the network.

STP helps maintain a **loop-free logical topology** while still allowing **physical redundancy** for backup connections.
