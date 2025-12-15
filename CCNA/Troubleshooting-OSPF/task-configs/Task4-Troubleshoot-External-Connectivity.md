# Task4 Troubleshoot External Connectivity.md 🌍🧪

## 🎯 Goal
PC1 and PC2 cannot ping the external server **8.8.8.8**.  
Troubleshoot where the traffic stops, fix the routing issue, and restore end-to-end connectivity.

## Topology For Reference

<img width="707" height="307" alt="topololgy" src="https://github.com/user-attachments/assets/5f516c89-9322-44b4-8128-ff659905e275" />

---

### 1️⃣ On PC1: Ping the external server

### 🔷 In command prompt:

```bash
ping 8.8.8.8
```

**Expected Ouput✅:**

<img width="749" height="408" alt="T4-pc1-ping-filed" src="https://github.com/user-attachments/assets/57059b18-c4c3-4029-8234-4c619efd37e6" />

PC1 ping failed

### 2️⃣ On PC2: Ping the external server

```bash
ping 8.8.8.8
```

**Expected Ouput✅:**

<img width="745" height="367" alt="T4-pc2-ping-filed" src="https://github.com/user-attachments/assets/aa672911-e071-4fc4-b65f-5650bc61fed1" />

## Trace Where the Packet Stops

### 3️⃣ From PC1: Run traceroute

### 🔷 In command prompt:

```bash
tracert 8.8.8.8
```

**Expected Ouput✅:**

<img width="740" height="378" alt="T4-pc1-tracert" src="https://github.com/user-attachments/assets/d83a1c8c-e0c1-476c-be1b-ec7a44f1e7cc" />

Note the packet stops when it reach the default gateway (10.0.1.254), then request time out displays

### 4️⃣ From PC2: Run traceroute

### 🔷 In command prompt:

```bash
tracert 8.8.8.8
```

**Expected Ouput✅:**

<img width="749" height="318" alt="T4-pc2-tracert" src="https://github.com/user-attachments/assets/a28cc9c6-e4fd-4853-9268-18b652bda297" />




