# 🔐 Task 4 - Configure R1 as NTP Master (Stratum 8) + Authenticate R2/R3 (Includes Task 5)

## 🎯 Goal
Configure **R1** as a **Stratum 8 NTP master**, then synchronize **R2** and **R3** to **R1** using **NTP authentication**.  
Because Packet Tracer does **not support `ntp source`**, use **R1’s physical interface IP addresses** as the NTP server addresses.

✅ **Task 5 is included here:** Configure NTP to update the **hardware calendar** on the routers (note: you can’t view the calendar in Packet Tracer).

## Topology For Refernece

<img width="648" height="256" alt="topology" src="https://github.com/user-attachments/assets/e30bc4fe-1d0b-480f-82fd-509165d35916" />

---

## ⚠️ Packet Tracer Note (Important)
- The command `ntp source` is **not available** in Packet Tracer.
- So instead of using a loopback, configure **R2/R3** to point to **R1’s physical interface IPs**.

---

## 🧩 Configure R1, R2, and R3

### 1️⃣ Enter Privileged EXEC Mode (All Routers)

```bash
enable
```

## 🟦 Part A - Configure R1 as Stratum 8 NTP Master

### 2️⃣ Enter Global Configuration Mode (R1)

```bash
configure terminal
```

### 3️⃣ Configure R1 as an NTP Master (Stratum 8)

```
ntp master
```

## 🟩 Part B - Configure NTP Authentication (R1, R2, R3)

```bash
ntp authenticate
ntp authentication-key 1 md5 ccnalab
ntp trusted-key 1
```

**Note: 🔐 The key number and password must match on all routers**

