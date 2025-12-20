# Task2C Block 172.16.1.0 hosts to 172.16.2.0 🚫🛡️

## 🎯 Goal
Prevent **hosts in the 172.16.1.0/24 network** from accessing  
the **172.16.2.0/24 network**, while allowing all other traffic.

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
access-list 1 deny 172.16.1.0 0.0.0.255
access-list 1 permit any
```

**Note:** 📝 This ACL denies traffic sourced from 172.16.1.0/24 and permits all other sources.

### 4️⃣ Apply the ACL outbound on R1 g0/1

```bash
interface g0/1
ip access-group 1 out
```

### 5️⃣ Exit configuration mode

```bash
end
```

---

## Test the Policy

### From PC1 (172.16.1.1) ping PC3 (172.16.2.1)

<img width="748" height="332" alt="T2C-PC1-PC3-failed" src="https://github.com/user-attachments/assets/2ac6a83e-efb9-4528-b305-f56d895ac976" />

### Verify ACL

```bash
show access-lists
```

**Expected Ouput✅:**

<img width="553" height="145" alt="T2C-verify-acl" src="https://github.com/user-attachments/assets/fa5591ae-fb3b-48e6-9a74-44aca6476fe2" />

**Note:** I took this screenshot after finising the lab. You should only see the first ACL
