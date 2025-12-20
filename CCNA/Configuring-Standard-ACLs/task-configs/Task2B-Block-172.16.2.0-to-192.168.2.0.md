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
ip access-list standard BLOCK-172.16.2.0
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
ip access-group BLOCK-172.16.2.0 out
```

---

## 🧪 Test the Policy


