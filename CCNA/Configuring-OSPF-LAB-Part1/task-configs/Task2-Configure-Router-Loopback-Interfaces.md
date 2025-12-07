# Task2 - Configure-Router-Loopback-Interfaces.md

## 🎯 Goal

In this task I will configure a **Loopback0 interface** on each router and assign a /32 IP address:

- R1 → `1.1.1.1/32`
- R2 → `2.2.2.2/32`
- R3 → `3.3.3.3/32`
- R4 → `4.4.4.4/32`

## Topology For Reference

<img width="711" height="341" alt="Topology" src="https://github.com/user-attachments/assets/53e6080d-57be-4f5f-b410-c3046016c538" />

Loopback interfaces are always up (as long as they are configured), so they are useful as a router IDs and test IPs in OSPF.

---

## 🖥️ R1: Configure Loopback0

### 1️⃣ **Enter global configuration mode:**

```bash
enable
configure terminal
```

### 2️⃣ Create Loopback0 and assign the IP

```bash
interface loopback0
ip address 1.1.1.1 255.255.255.255
```

### 3️⃣ Verify the interface

```bash
do show ip int brief
```

**Expected Output✅:**

<img width="874" height="140" alt="T2-R1-ip-int" src="https://github.com/user-attachments/assets/371f7479-29b5-4833-9cbd-53f3edd57595" />

---

## 🖥️ R2: Configure Loopback0

### 1️⃣ **Enter global configuration mode:**

```bash
enable
configure terminal
```

### 2️⃣ Create Loopback0 and assign the IP

```bash
interface loopback0
ip address 2.2.2.2 255.255.255.255
```

### 3️⃣ Verify the interface

```bash
do show ip int brief
```

**Expected Output✅:**

<img width="823" height="119" alt="T2-R2-ip-int" src="https://github.com/user-attachments/assets/63533b49-9caa-4667-8545-a1c4743a5267" />

