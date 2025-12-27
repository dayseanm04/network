# 🌐 Task 3 - Configure External NTP Server

## 🎯 Goal
Configure **R1** to synchronize time with an **external NTP server (1.1.1.1)** over the Internet.  
Then verify **NTP synchronization** and identify the **stratum levels** of both the server and R1.

## Topology For Refernece

<img width="648" height="256" alt="topology" src="https://github.com/user-attachments/assets/e30bc4fe-1d0b-480f-82fd-509165d35916" />

---

## 🧩 Configure R1

### 1️⃣ Enter Global Configuration Mod (R1)

```bash
enable
configure terminal
```

### 2️⃣ Configure External NTP Server (R1)

```bash
ntp server 1.1.1.1
```

**Note: ℹ️ This command configures R1 as an NTP client using 1.1.1.1 as its time source.**


### 3️⃣ Allow Time for NTP Synchronization
- In Packet Tracer, fast-forward the simulation time to allow synchronization to occur.
- ⏩ NTP synchronization does not happen instantly in Packet Tracer.

