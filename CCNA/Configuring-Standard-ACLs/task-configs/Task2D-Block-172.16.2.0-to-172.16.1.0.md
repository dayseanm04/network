# Task2D Block 172.16.2.0 hosts to 172.16.1.0 🚫🛡️

## 🎯 Goal
Prevent **hosts in the 172.16.2.0/24 network** from accessing  
the **172.16.1.0/24 network**, while allowing all other traffic.

---

## Topology For Reference

<img width="734" height="267" alt="topology" src="https://github.com/user-attachments/assets/57bf3181-0365-471e-a3e5-86c4aab1af4e" />

## Configure R1

### 1️⃣ Enter privileged EXEC mode

```bash
enable
```

### 2️⃣Enter global configuration mode

```bash
configure terminal
```

### 3️⃣ Create a standard numbered ACL

```bash
access-list 2 deny 172.16.2.0 0.0.0.255
access-list 2 permit any
```

### 4️⃣ Apply the ACL outbound on R1 g0/0

```bash
interface g0/0
ip access-group 2 out
```

### 5️⃣ Exit configuration mode

```bash
end
```

---

## Test the Policy

### From PC3 (172.16.2.1) ping PC1 (172.16.1.1)

<img width="748" height="339" alt="T2D-PC3-PC1-ping-fail" src="https://github.com/user-attachments/assets/c5baedba-44e5-4bd8-87b5-c0cfe42f011e" />

### Verify ACL

```bash
show access-lists
```

**Expected Ouput✅:**

<img width="553" height="145" alt="T2d-verify-acl" src="https://github.com/user-attachments/assets/fa5591ae-fb3b-48e6-9a74-44aca6476fe2" />
