# 🛣️ Task 4: R1 Static Route Configuration

Objective: Configure **static routes on R1** so that PCs in LAN3 and LAN4 can be reached.  

## 📋 R1 Static Routes Table

| Destination Network | Subnet Mask        | Next Hop       | Interface |
|--------------------|------------------|----------------|-----------|
| 192.168.5.192/27 (LAN3) | 255.255.255.224  | 192.168.5.242  | g0/0/0   |
| 192.168.5.224/28 (LAN4)  | 255.255.255.240  | 192.168.5.242  | g0/0/0   |
---

## Step-by-Step Configuration of Static Routes on R1

### 1️⃣ Enter Global Configuration Mode  

```bash
en
conf t
```

---

### 2️⃣ Configure Static Route to LAN3 (192.168.5.192/27)
```bash
ip route 192.168.5.192 255.255.255.224 192.168.5.242
```

---

### 3️⃣ Configure Static Route to LAN4 (192.168.5.224/28)

```bash
ip route 192.168.5.224 255.255.255.240 192.168.5.242
exit
```

### 4️⃣ Verify the Routes
```bash
show ip route
```

### Expected output ✅

<img width="713" height="413" alt="R1-route" src="https://github.com/user-attachments/assets/8247a172-7762-4d81-80c0-84e6aa7589c2" />
