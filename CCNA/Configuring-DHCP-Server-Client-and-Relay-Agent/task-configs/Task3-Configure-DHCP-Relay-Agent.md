# 📬 Task 3 – Configure R1 as a DHCP Relay Agent (192.168.1.0/24)

## 🎯 Goal
Configure **R1** as a **DHCP relay agent** so that clients in the **192.168.1.0/24** network can receive DHCP addresses from the DHCP server **R2**. Because DHCP messages are broadcasts, they normally do **not** cross routers. A relay agent forwards those DHCP requests to the DHCP server using an **ip helper-address**.

## Topology For Reference

<img width="645" height="285" alt="Topology" src="https://github.com/user-attachments/assets/21f639d4-6d6f-4952-9de3-d255df077e99" />

---

## ✅ Configure R1

### 1️⃣ Enter Global Config Mode

```bash
enable
configure terminal
```



### 2️⃣ Enter the LAN Interface for 192.168.1.0/24

```bash
interface g0/1
```

### 3️⃣ Configure the DHCP Relay (Helper Address)

```bash
ip helper-address 203.0.113.1
```

**Note: ✅ This forwards DHCP requests from the R1 G0/1 side to R2.**



## 🔍 Verification 

### On R1

```bash
show running-config | section GigabitEthernet0/1
```

**Expected Output:**

<img width="568" height="120" alt="T3-show-run-config" src="https://github.com/user-attachments/assets/8e3336be-9d92-44ec-b1a1-132c7015e298" />

### 4️⃣ Exit and Save (Recommended)

```bash
write memory
```
