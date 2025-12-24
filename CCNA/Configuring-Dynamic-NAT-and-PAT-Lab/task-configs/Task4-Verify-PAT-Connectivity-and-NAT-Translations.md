# 🌐 Task 4 – Verify PAT Connectivity and NAT Translations

## 🎯 Goal
Verify that **PAT (NAT Overload)** is working correctly by testing internet connectivity from **all internal hosts** and examining the **NAT translation table** on R1.

After switching from Dynamic NAT to PAT, **PC1, PC2, and PC3 should all be able to access the internet at the same time** using a single public IP address.

## Topology For Reference

<img width="588" height="215" alt="Topology" src="https://github.com/user-attachments/assets/a0ad75ab-6982-416a-8c01-5fd83306f1b0" />

## ✅ Ping Tests

### 1️⃣ Ping google.com from PC1

**First ping 8.8.8.8 then ping google.com:**

**Expected Output:✅**

<img width="746" height="364" alt="PC1-ping-google" src="https://github.com/user-attachments/assets/1ebfaf39-9588-4775-bb3e-70f681dab90a" />

---

### 2️⃣ Ping google.com from PC2

**First ping 8.8.8.8 then ping google.com:**

**Expected Output:✅**

<img width="745" height="362" alt="PC2-ping-google" src="https://github.com/user-attachments/assets/5dd33651-133a-42bc-bd5a-5002b6253bd2" />

---

### 3️⃣ Ping google.com from PC3

**First ping 8.8.8.8 then ping google.com:**

**Expected Output:✅**

<img width="750" height="403" alt="PC3-google-ping" src="https://github.com/user-attachments/assets/fa7be919-d985-446d-bf7a-9449af9d39d0" />

---

## View NAT translations

```bash
show ip nat translations
```

<img width="783" height="259" alt="T4-show-nat-translations" src="https://github.com/user-attachments/assets/16cdf53c-af0c-437d-be66-51dfd06104a6" />
