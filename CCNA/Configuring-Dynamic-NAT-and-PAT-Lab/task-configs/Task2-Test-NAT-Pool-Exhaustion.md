# 🧪 Task 2 – Test NAT Pool Exhaustion (Dynamic NAT)

## 🎯 Goal
Test what happens when the **Dynamic NAT pool runs out of available public IP addresses**.

In this lab, the NAT pool only has **two public IPs** (`100.0.0.1` and `100.0.0.2`). 
That means only **two inside hosts** can successfully access the internet at the same time using Dynamic NAT.
When a third host tries, it should fail.

## Topology For Reference

<img width="588" height="215" alt="Topology" src="https://github.com/user-attachments/assets/a0ad75ab-6982-416a-8c01-5fd83306f1b0" />

---

### 1️⃣ Ping google.com from PC1

**First ping 8.8.8.8 then ping google.com:**


**✅ Expected Output:**

<img width="746" height="364" alt="PC1-ping-google" src="https://github.com/user-attachments/assets/e6dacb53-e61c-4329-8f81-60f2c3f57d0b" />

### 2️⃣ Ping google.com from PC2

**First ping 8.8.8.8 then ping google.com:**


**✅ Expected Output:**

<img width="745" height="362" alt="PC2-ping-google" src="https://github.com/user-attachments/assets/a9f4a32a-c8c5-4d6d-bb59-14aea2697519" />

### 3️⃣ Ping google.com from PC3

**First ping 8.8.8.8 then ping google.com:**


**✅ Expected Output:**

<img width="744" height="369" alt="PC3-GOOG-ping" src="https://github.com/user-attachments/assets/34ebb5e4-8d5b-48fa-8777-6d703f65b265" />

<img width="738" height="182" alt="PC3-google-ping" src="https://github.com/user-attachments/assets/90142434-5641-475b-bdd2-d2f340950a8b" />

PC3 ping failed because the NAT pool is exhausted.


## View NAT translations

```bash
show ip nat translations
```

<img width="767" height="356" alt="T2-R1-nat-translations" src="https://github.com/user-attachments/assets/0699452c-32be-4a64-8a88-17767d8ff4cf" />
