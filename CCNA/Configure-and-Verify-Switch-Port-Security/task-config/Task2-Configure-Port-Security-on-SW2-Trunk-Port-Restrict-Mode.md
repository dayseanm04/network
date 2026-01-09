# 🔀 Task 1B – Configure Port Security on SW2 Trunk Port with Sticky MAC Learning

## 📌 Objective

Configure **port security** on the **trunk interface** on **SW2** using:
- **Restrict** violation mode
- **Sticky MAC address learning**
- Support for **multiple MAC addresses**

This task demonstrates how port security behaves differently on a **trunk port** compared to access ports.

## 🧠 Simple Explanation

- The trunk link connects **SW2 to SW1**
- Multiple MAC addresses are expected on a trunk
- **Restrict mode** blocks unauthorized MAC addresses **without shutting down** the interface
- **Sticky MAC learning** automatically learns and saves MAC addresses

📌 This configuration allows normal operation while still providing **Layer 2 security**.

## Topology For Reference

<img width="589" height="226" alt="topology" src="https://github.com/user-attachments/assets/1377e3a8-db00-45d9-b90c-5b3d92a36807" />

---

