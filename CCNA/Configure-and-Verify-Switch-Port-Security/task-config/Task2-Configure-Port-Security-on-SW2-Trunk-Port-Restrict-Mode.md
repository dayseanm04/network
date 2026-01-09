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

## 🔐 Port Security Policy (SW2 G0/1)

| Setting | Value |
|------|------|
| Violation Mode | ⚠️ Restrict |
| Maximum MAC Addresses | 4 |
| Sticky MAC Learning | Enabled |

📌 **Why 4 MAC addresses?**  

The trunk receives MAC addresses from:
- Multiple PCs (PC1, 2, and 3)
- The neighboring switch

---

## ⚙️ Configuration Steps

### 1️⃣ Enter Global Configuration Mode

```bash
configure terminal
```

### 2️⃣ Select the Trunk Interface

```bash
interface g0/1
```

### 3️⃣ Configure the Interface as a Trunk

```bash
switchport mode trunk
```

### 4️⃣ Enable Port Security

```bash
switchport port-security
```

### 5️⃣ Set Violation Mode to Restrict

```bash
switchport port-security violation restrict
```

### 6️⃣ Set Maximum Allowed MAC Addresses

```bash
switchport port-security maximum 4
```








