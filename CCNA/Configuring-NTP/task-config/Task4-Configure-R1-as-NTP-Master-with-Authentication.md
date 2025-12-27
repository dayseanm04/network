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

### 2️⃣ Enter Global Configuration Mode (R1, R2, and R3)

```bash
configure terminal
```

### 3️⃣ Configure R1 as an NTP Master (Stratum 8)

```
ntp master
```

## 🟩 Part B - Configure NTP Authentication (R1, R2, R3)

### 4️⃣ Enable NTP Authentication + Create Key (R1)

```bash
ntp authenticate
ntp authentication-key 1 md5 ccnalab
ntp trusted-key 1
```

### 5️⃣ Enable NTP Authentication + Create Key (R2 and R3)

```bash
ntp authenticate
ntp authentication-key 1 md5 ccnalab
ntp trusted-key 1
```

**Note: 🔐 The key number and password must match on all routers**

## 🟨 Part C - Point R2 and R3 to R1 Using Physical Interface IPs

### 6️⃣ Configure R2 and R3 to Use R1 as NTP Server (Use R1 Physical IPs)

```bash
ntp server 192.168.13.1 key 1
ntp server 192.168.12.1 key 1
```

### 7️⃣ Allow Time for Synchronization
- In Packet Tracer, fast-forward time so NTP can sync.
- ⏩ NTP may take time to form associations and synchronize.


### 8️⃣ Verify NTP Associations (R2 and R3)

**On R2 do show ntp associations**

**Expected output✅:**

<img width="1002" height="150" alt="T4-T3-show-ntp-associations" src="https://github.com/user-attachments/assets/d868f488-02ce-4f22-9db6-d3e48a95efe7" />

**On R3 do show ntp associations**

**Expected output✅:**

<img width="994" height="152" alt="T4-R3-show-ntp-ass" src="https://github.com/user-attachments/assets/d0a3d544-d40d-40a4-8575-8d55b0f5ea31" />


### 9️⃣ Verify Clocks Match (R1 vs R2/R3)

**On R1 and R2, compare:**

```bash
show clock
```

<img width="696" height="82" alt="T4-R2-R1-sync" src="https://github.com/user-attachments/assets/ace30d66-2df2-4e20-9c4e-cca48ac4da80" />



