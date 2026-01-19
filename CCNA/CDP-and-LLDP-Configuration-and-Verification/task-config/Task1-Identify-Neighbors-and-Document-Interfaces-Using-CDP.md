# 🔍 Task 1 Identify Neighbors and Document Interfaces Using CDP

## 📌 Objective
Use **CDP** (and show commands) to identify and label the **missing IP addresses** and **interface** of the devices in the topology.

# Topology For Reference

<img width="564" height="278" alt="topology" src="https://github.com/user-attachments/assets/cec8d912-5346-4e0a-a7d2-fc793f76f1c1" />

## 🛠️ Commands to Use (Run on Each Network Device)

### 1️⃣ Check CDP Neighbors

Run on **R1, R2, R3**:

```bash
show cdp neighbors
```

Run on **SW1, SW2, SW3**:

```bash
show cdp neighbors
```

### 2️⃣ Check Interface IP Addresses (Routers)

```bash
show ip interface brief
```

### 3️⃣ Check End-Device IP Settings (PCs)

On PC1, PC2, PC3:
- Go to Desktop → IP Configuration
- Or in Command Prompt: ipconfig

## Reference labeled topoology:

<img width="823" height="355" alt="T1-Net-with-labels" src="https://github.com/user-attachments/assets/b6575536-27f6-4e52-8ec6-87ae60bff4b2" />






