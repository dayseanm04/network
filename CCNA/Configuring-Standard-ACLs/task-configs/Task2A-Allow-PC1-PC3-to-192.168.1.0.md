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

**📌 Note:** This policy is enforced closest to the **destination network (192.168.1.0/24)** using a **standard named ACL** on **R2**.



## Test the Policy

### From PC1 (172.16.1.1) ping SRV1 (192.168.1.100)

<img width="746" height="370" alt="T2A-ACL-test-PC1" src="https://github.com/user-attachments/assets/e0cf4d56-b5c4-499d-b1a0-7aafc3c28494" />

Ping test was succesfull for PC1

### From PC3 (172.16.2.1) ping SRV1 (192.168.1.100)

<img width="742" height="376" alt="T2A-PC3-SR1-ping-sucess" src="https://github.com/user-attachments/assets/d608c8b9-3820-4dd0-8f94-a19d84536135" />

Ping test was succesfull for PC1

### From PC2 (172.16.1.2) ping SRV1 (192.168.1.100)

<img width="743" height="323" alt="T2A-PC2-ping-test" src="https://github.com/user-attachments/assets/2c53bbd9-fb33-4bef-836b-7aea7107d6f3" />

The ping was successfuly blocked by R2

#### Verify ACL

```bash
show access-lists
```

**Expected Ouput✅:**

<img width="581" height="147" alt="T2a-verify-acl" src="https://github.com/user-attachments/assets/f26f59d5-bd7c-41df-8616-164b841aae59" />

**Note:** I took this screenshot after finising the lab. You should only see the second ACL
