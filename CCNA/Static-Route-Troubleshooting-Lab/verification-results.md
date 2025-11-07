# ✅ Verification Results: Static Route Troubleshooting Lab

## 🧭 Objective
To verify that **all routing misconfigurations have been corrected** and that **PC1 and PC2 can successfully communicate with each other**.

---

## 🧩 Connectivity Verification

### 🖥️ PC1 → PC2 Ping Test
- **Action:** Ping **PC2 (192.168.3.1)** from **PC1 (192.168.1.1)**.

<img width="737" height="376" alt="PC1-PC2-Ping" src="https://github.com/user-attachments/assets/fa59486e-1379-4453-a6de-d7c34dca57b7" />

- **Expected Result:** Successful ICMP echo replies.
- **Result:** ✅ PC1 successfully pinged PC2.

---

### 🖥️ PC2 → PC1 Ping Test
- **Action:** Ping **PC1 (192.168.1.1)** from **PC2 (192.168.3.1)**.

<img width="737" height="398" alt="PC2-PC1-Ping" src="https://github.com/user-attachments/assets/07edd3af-fecf-44d2-89a2-a1e92409c45c" />

- **Expected Result:** Successful ICMP echo replies.
- **Result:** ✅ PC2 successfully pinged PC1.
