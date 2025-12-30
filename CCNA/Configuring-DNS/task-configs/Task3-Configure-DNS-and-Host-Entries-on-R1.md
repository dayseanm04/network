# 🛠️ Task 3 – Configure DNS + Host Entries on R1 (Then Ping PC1 by Name)

## 🎯 Goal
Configure **R1** to use **1.1.1.1** as its DNS server, then create **local host entries** on R1 for:
- R1
- PC1
- PC2
- PC3

Finally, verify name resolution by pinging **PC1 by name** from R1. 

## Topology For Reference

<img width="626" height="254" alt="Topology" src="https://github.com/user-attachments/assets/7c66d56e-4913-4f1f-97fa-fa7b65588bf3" />

---


## ✅ Configure (R1)

### 1️⃣ Enter Global Configuration Mode

```bash
enable
configure terminal
```

--

### 2️⃣ Configure R1 to Use 1.1.1.1 as DNS Server

```bash
ip name-server 1.1.1.1
```

### 3️⃣ Configure Local Host Entries on R1

```bash
ip host PC1 192.168.0.1
ip host PC2 192.168.0.2
ip host PC3 192.168.0.3
ip host R1 192.168.0.254
````

### 4️⃣ Save the Configuration (Recommended)

```bash
end
write memory
```

---

## 🔍 Verification

### 5️⃣ Verify Host Entries on R1

#### ♦️ On R1, check the configured host table:

```bash
show hosts
```

<img width="713" height="279" alt="T3-R1-show-hosts" src="https://github.com/user-attachments/assets/0a9343b2-eab6-4b30-9435-16d2238470ca" />

---

### 6️⃣ Ping PC1 by Name from R1

#### ♦️ On R1, ping PC1 using its hostname:

```bash
ping PC1
```

<img width="697" height="170" alt="T3-Ping-PC1" src="https://github.com/user-attachments/assets/02e38f73-ba22-487b-83c6-39a19975d00a" />

The Ping was successfull


## 🧠 Key Takeaway
- `ip host` entries let R1 resolve names **locally** (without contacting external DNS)
- `ip name-server 1.1.1.1` allows R1 to resolve **internet domain names** when needed
