# 🛠️ Task 1 – Configure-Port-Security-on-SW1-Access-Ports-Shutdown-Mode

## 📌 Objective

Configure **strict port security** on **SW1 access ports** to allow **only one device per port**.
If a violation occurs, the interface will be **shut down immediately**.

This task demonstrates how port security can **prevent unauthorized devices** from accessing the network.

## 🧠 Simple Explanation

- Each access port should only allow **one MAC address**
- If another device is detected:
  - The port goes into **err-disabled (shutdown)** state
- Sticky learning is **disabled**, so MAC addresses are **not automatically saved**

## Topology For Reference

<img width="589" height="226" alt="topology" src="https://github.com/user-attachments/assets/1377e3a8-db00-45d9-b90c-5b3d92a36807" />

---


## 🔐 Port Security Policy (SW1)

| Setting | Value |
|------|------|
| Violation Mode | 🚫 Shutdown |
| Maximum MAC Addresses | 1 |
| Sticky MAC Learning | Disabled |
| Aging Time | ⏱️ 1 hour |

---

## ⚙️ Configuration Steps

### 1️⃣ Enter Global Configuration Mode

```bash
enable
configure terminal
```

### 2️⃣ Select the Access Interfaces

```bash
interface range f0/1 - 3
```

### Enable Port Security

```bash
switchport port-security
```

**Expected Output:**

<img width="563" height="97" alt="T1-A-Log" src="https://github.com/user-attachments/assets/63a7a280-495c-4f47-b2cf-a069a2037952" />














