# ✅ Verification Results: Static Route Troubleshooting Lab

## 🧭 Objective
To verify that **all routing misconfigurations have been corrected** and that **PC1 and PC2 can successfully communicate with each other**.

---

## 🧩 Connectivity Verification

### 🖥️ PC1 → PC2 Ping Test
- **Action:** Ping **PC2 (192.168.3.1)** from **PC1 (192.168.1.1)**.

<img width="742" height="373" alt="PC1-PC2-Ping" src="https://github.com/user-attachments/assets/04d96448-18df-494d-8f8f-ad8d46244648" />

- **Expected Result:** Successful ICMP echo replies.
- **Result:** ✅ PC1 successfully pinged PC2.

---

### 🖥️ PC2 → PC1 Ping Test
- **Action:** Ping **PC1 (192.168.1.1)** from **PC2 (192.168.3.1)**.


<img width="733" height="411" alt="PC2-PC1-Ping" src="https://github.com/user-attachments/assets/0e8ebd50-4169-42cb-94b1-70adf479266f" />

- **Expected Result:** Successful ICMP echo replies.
- **Result:** ✅ PC2 successfully pinged PC1.
