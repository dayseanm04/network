# 🛠️ Task 1 – Configure Access Ports for Data and Voice VLANs

## 📌 Objective

Configure the **access switch ports** so they can carry **both data and voice traffic** using:
- A **Data VLAN** for PCs
- A **Voice VLAN** for IP Phones

This allows a **PC and an IP phone to share the same physical switch port** while keeping their traffic logically separated.

## Topology For Reference

<img width="657" height="253" alt="topology" src="https://github.com/user-attachments/assets/3459f83e-c98d-4bca-826a-c8d8641898e7" />

---

## 🧠 Simple Explanation

- **PC traffic** belongs to the **Data VLAN**
- **IP phone traffic** belongs to the **Voice VLAN**
- The switch:
  - Sends **untagged traffic** to the PC
  - Sends **802.1Q-tagged traffic** to the IP phone
 
---

## 📋 VLAN Information

| VLAN Type | VLAN ID | Purpose |
|---------|--------|--------|
| 🖥️ Data VLAN | 10 | PC data traffic |
| 📞 Voice VLAN | 20 | IP phone voice traffic |

---

## 🔌 Interface Connections

| Switch Interface | Connected Device |
|-----------------|------------------|
| G1/0/2 | IP Phone (PH1) → PC1 |
| G1/0/3 | IP Phone (PH2) → PC2 |

📌 The PC is connected **through** the IP phone.

---

## ⚙️ Configuration Steps

### 1️⃣ Enter Global Configuration Mode

```bash
enable
configure terminal
```

### 2️⃣ Select the Access Interfaces

```bash
interface range g1/0/2 - 3
```

### 3️⃣ Configure the Interfaces as Access Ports

```bash
switchport access vlan 10
```


