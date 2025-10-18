# 🛣️ Task 4: R2 Static Route Configuration

Objective: Configure **static routes on R2** so that PCs in LAN1 and LAN2 can be reached.  

## 📋 R2 Static Routes Table

| Destination Network | Subnet Mask        | Next Hop       | Interface |
|--------------------|------------------|----------------|-----------|
| 192.168.5.128/26 (LAN1) | 255.255.255.192  | 192.168.5.241  | g0/0/0   |
| 192.168.5.0/25 (LAN2)  | 255.255.255.128  | 192.168.5.241  | g0/0/0   |
---

## Step-by-Step Configuration of Static Routes on R2

### 1️⃣ Enter Global Configuration Mode  
```bash
en
conf t
```

---

### 2️⃣ Configure Static Route to LAN1 (192.168.5.128/26)
```bash
ip route 192.168.5.128 255.255.255.192 192.168.5.241
```

---

### 3️⃣ Configure Static Route to LAN2 (192.168.5.0/25)

```bash
ip route 192.168.5.0 255.255.255.128 192.168.5.241
exit
```

### 4️⃣ Verify the Routes
```bash
show ip route
```

### Expected output ✅

<img width="711" height="413" alt="R2-route" src="https://github.com/user-attachments/assets/2cf1400f-2e69-4bc7-a0eb-1d6549482da5" />
