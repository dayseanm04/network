# 🧪 Task 3 – Test Connectivity After NAT (PC1 ➜ 8.8.8.8)

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

---

**Note: the ping test was successful after I configured Static NAT**

## 🧠 Why This Works
- Static NAT translates PC1’s **private IP address** into a **public IP address**
- This allows return traffic from the internet to reach PC1 correctly
- Without NAT, the internet cannot route traffic back to private IPs
