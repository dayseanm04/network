# Task2A Allow PC1 and PC3 to 192.168.1.0.md 🚦🛡️

## 🎯 Goal
Configure a **standard numbered ACL on R1** so that **only PC1 and PC3** are allowed to access the **192.168.1.0/24** network.  
All other sources should be denied by this policy.

## Topology For Reference

<img width="734" height="267" alt="topology" src="https://github.com/user-attachments/assets/57bf3181-0365-471e-a3e5-86c4aab1af4e" />

## Configure R2

### 1️⃣ Enter privileged EXEC mode

```bash
enable
```

### 2️⃣Enter global configuration mode

```bash
configure terminal
```

### 3️⃣ Create a standard named ACL that only permits PC1 and PC3

```bash
ip access-list standard ALLOW-PC1-PC3
permit 172.16.1.1
permit 172.16.2.1
deny any
```

### 4️⃣ Apply the ACL to R2 g0/0 outbound (toward 192.168.1.0/24)

```bash
interface g0/0
ip access-group ALLOW-PC1-PC3 out
```

