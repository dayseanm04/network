# 🌍 Task 1 – Configure Default Route on R1

## 🎯 Goal
Configure a **default route** on **R1** so it can reach the **Internet**.  
This step is required for **DNS resolution and external connectivity** to work in later tasks.

## 🧠 Why This Matters
- DNS servers (like `1.1.1.1`) are **outside** the local network
- Without a default route, R1 **does not know where to send Internet traffic**

## Topology For Reference

<img width="626" height="254" alt="Topology" src="https://github.com/user-attachments/assets/7c66d56e-4913-4f1f-97fa-fa7b65588bf3" />

---

## ✅ Configure (R1)

### 1️⃣ Enter Global Configuration Mode

```bash
enable
configure terminal
```
---

### 2️⃣ Configure the Default Route

```bash
ip route 0.0.0.0 0.0.0.0 203.0.113.2
```

**Note📌: This tells R1: Send all unknown traffic to 203.0.113.2.**

---

### 3️⃣ Exit and Save the Configuration

```bash
end
write memory
```

---

## 🔍 Verification 

### 4️⃣ Verify the Routing Table

```bash
show ip route
```

<img width="843" height="338" alt="T1-show-ip-route" src="https://github.com/user-attachments/assets/c9bbbd2b-3efa-4d39-9ad7-6260bc026030" />















