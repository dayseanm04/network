# 📡 Task 1 – Configure DHCP Pools on R2

## 🎯 Goal
Configure **three DHCP pools** on **R2** so it can assign IP addresses to multiple networks, while reserving specific addresses that should NOT be handed out by DHCP.

## Topology For Reference

<img width="645" height="285" alt="Topology" src="https://github.com/user-attachments/assets/21f639d4-6d6f-4952-9de3-d255df077e99" />


### I will configure:
- ✅ **POOL1** for `192.168.1.0/24` (reserve `.1`–`.10`)
- ✅ **POOL2** for `192.168.2.0/24` (reserve `.1`–`.10`)
- ✅ **POOL3** for `203.0.113.0/30` (reserve `.1`)

## 🗺️ DHCP Pool Requirements

### ✅ POOL1 – **192.168.1.0/24**
| Setting | Value |
|--------|------|
| Excluded Range | `192.168.1.1` → `192.168.1.10` |
| DNS | `8.8.8.8` |
| Domain | `jeremysitlab.com` |
| Default Gateway | `192.168.1.1` (R1) |

---

### ✅ POOL2 – **192.168.2.0/24**
| Setting | Value |
|--------|------|
| Excluded Range | `192.168.2.1` → `192.168.2.10` |
| DNS | `8.8.8.8` |
| Domain | `jeremysitlab.com` |
| Default Gateway | `192.168.2.1` (R2) |

---

### ✅ POOL3 – **203.0.113.0/30**
| Setting | Value |
|--------|------|
| Excluded Address | `203.0.113.1` |
| Network | `203.0.113.0/30` (`255.255.255.252`)|

---

## ✅ Configure R2

### 1️⃣ Enter Global Configuration Mode

```bash
enable
configure terminal
```

## 🧩 Configure POOL1 (192.168.1.0/24)

### 2️⃣ Exclude Reserved Addresses for POOL1

```bash
ip dhcp excluded-address 192.168.1.1 192.168.1.10
```

### 3️⃣ Create the DHCP Pool (POOL1)

```bash
ip dhcp pool POOL1
```

### 4️⃣  Set the Network for POOL1

```bash
network 192.168.1.0 255.255.255.0
```

### 5️⃣  Set the Domain Name for POOL1

```bash
domain-name jeremysitlab.com
```

### 6️⃣ Set the DNS Server for POOL1

```bash
dns-server 8.8.8.8
```

### 7️⃣ Set the Default Gateway for POOL1 (R1)

```bash
default-router 192.168.1.1
exit
```

---

## 🧩 Configure POOL2 (192.168.2.0/24)

### 1️⃣ Exclude Reserved Addresses for POOL2

```bash
ip dhcp excluded-address 192.168.2.1 192.168.2.10
```

### 2️⃣ Create the DHCP Pool (POOL2)

```bash
ip dhcp pool POOL2
```

### 3️⃣ Set the Network for POOL2

```bash
network 192.168.2.0 255.255.255.0
```

### 4️⃣ Set the Domain Name for POOL2

```bash
domain-name jeremysitlab.com
```

### 5️⃣ Set the DNS Server for POOL1

```bash
dns-server 8.8.8.8
```

### 6️⃣ Set the Default Gateway for POOL1 (R1)

```bash
default-router 192.168.2.1
exit
```























