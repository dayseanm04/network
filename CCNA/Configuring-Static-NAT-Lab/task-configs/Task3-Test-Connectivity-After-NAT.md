# 🧪 Task 3 – Test Connectivity After NAT (PCs ➜ 8.8.8.8)

## 🎯 Goal
Verify that **Static NAT is working** by testing internet connectivity **after NAT configuration**. PC1 should now be able to successfully ping **8.8.8.8**.

## Topology For Reference

<img width="648" height="227" alt="Topology" src="https://github.com/user-attachments/assets/9eff3467-85fb-40f2-a50c-a3eca4d670d2" />

---

## ✅ On PC1

### 1️⃣ Open the Command Prompt on PC1

`ping 8.8.8.8`

**Expected Output✅**

<img width="739" height="363" alt="T3-PC1-Ping-Int-SRV" src="https://github.com/user-attachments/assets/ff799015-5c3c-40fb-9e8d-3525ded8b5f4" />

## ✅ On PC2

### 2️⃣ Open the Command Prompt on PC2

`ping 8.8.8.8`

**Expected Output✅**

<img width="745" height="380" alt="T3-PC2-Goog" src="https://github.com/user-attachments/assets/340f631b-7853-4a14-aa95-a21b27e1b157" />

<img width="739" height="363" alt="T3-PC1-Ping-Int-SRV" src="https://github.com/user-attachments/assets/ff799015-5c3c-40fb-9e8d-3525ded8b5f4" />

## ✅ On PC3

### 3️⃣ Open the Command Prompt on PC2

`ping 8.8.8.8`

**Expected Output✅**

<img width="745" height="376" alt="T3-PC3-Goog" src="https://github.com/user-attachments/assets/56bfd0c7-3b60-471d-94ad-14a8739c9cb2" />

---

**Note: the ping tests were successful after I configured Static NAT**

## 🧠 Why This Works
- Static NAT translates PC1’s **private IP address** into a **public IP address**
- This allows return traffic from the internet to reach PC1 correctly
- Without NAT, the internet cannot route traffic back to private IPs
