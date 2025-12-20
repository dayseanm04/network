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

## Test the Policy

### From PC1 (172.16.1.1) ping SRV1 (192.168.1.100)

<img width="746" height="370" alt="T2A-ACL-test-PC1" src="https://github.com/user-attachments/assets/e0cf4d56-b5c4-499d-b1a0-7aafc3c28494" />

Ping test was succesfull for PC1

### From PC3 (172.16.2.1) ping SRV1 (192.168.1.100)

<img width="743" height="323" alt="T2A-PC2-ping-test" src="https://github.com/user-attachments/assets/85b82ee5-b146-4a8d-9b0b-76e6ff604cec" />

Ping test was succesfull for PC1









