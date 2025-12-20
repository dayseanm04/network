# Task2B Block hosts in 172.16.2.0 to 192.168.2.0.md 🚫🛡️

## 🎯 Goal
Block **all hosts in the 172.16.2.0/24 network** from accessing the  
**192.168.2.0/24 network**, while allowing all other traffic.

---

## Topology For Reference

<img width="734" height="267" alt="topology" src="https://github.com/user-attachments/assets/57bf3181-0365-471e-a3e5-86c4aab1af4e" />


**📌 Note:** This policy is enforced closest to the **destination network (192.168.2.0/24)** using a **standard named ACL** on **R2**.

## Configure R2

### 1️⃣ Enter privileged EXEC mode

```bash
enable
```

### 2️⃣Enter global configuration mode

```bash
configure terminal
```

### 3️⃣ Create a standard named ACL

```bash
ip access-list standard block-172.16.2.0/24-hosts
```

### 4️⃣ Deny the 172.16.2.0/24 network

```bash
deny 172.16.2.0 0.0.0.255
```

### 5️⃣ Permit all other sources

```bash
permit any
```

### 6️⃣ Apply the ACL outbound on R2 g0/1

```bash
interface g0/1
ip access-group block-172.16.2.0/24 out
```

---

## 🧪 Test the Policy

### From PC3 (172.16.2.1) ping SRV2 (192.168.2.100)

<img width="747" height="329" alt="T2B-PC3-SR1-ping-failed" src="https://github.com/user-attachments/assets/74a88d25-c615-4667-b44c-248396e06e6a" />

**Note:** PC3 couldn't ping SRV2. Destination host unreachable,  the packet reaches the R2 but R2 doesn't forward it out of its G0/1 interface. The ACL denies it.

### From PC1 (172.16.1.1) ping SRV2 (192.168.2.100)

<img width="740" height="359" alt="T2b-PC1-ping-SVR2" src="https://github.com/user-attachments/assets/ff743c85-00b0-4878-a1cb-ec22c446c44b" />

Ping was successful

