# 🔍 Task 4 – Verify NAT Translations (google.com)

## 🎯 Goal
Verify that **Static NAT translations are being used** by generating internet traffic from all internal hosts and then checking the **NAT translation table on R1**.

## Topology For Reference

<img width="648" height="227" alt="Topology" src="https://github.com/user-attachments/assets/9eff3467-85fb-40f2-a50c-a3eca4d670d2" />

---

### 1️⃣ Ping google.com from PC1

`ping 8.8.8.8`

**Expected Output✅**

<img width="740" height="350" alt="T4-PC1-Goog" src="https://github.com/user-attachments/assets/98c54905-d491-4115-ab36-a614f55811d4" />

---

### 2️⃣ Ping google.com from PC2

`ping 8.8.8.8`

**Expected Output✅**

<img width="745" height="380" alt="T3-PC2-Goog" src="https://github.com/user-attachments/assets/340f631b-7853-4a14-aa95-a21b27e1b157" />

---

### 3️⃣ Open the Command Prompt on PC2

`ping 8.8.8.8`

**Expected Output✅**

<img width="745" height="376" alt="T3-PC3-Goog" src="https://github.com/user-attachments/assets/56bfd0c7-3b60-471d-94ad-14a8739c9cb2" />

### 4️⃣ Check NAT Translations on R1

```bash
show ip nat translation
```

**Expected Output✅**

<img width="791" height="304" alt="T4-check-NAT-translations" src="https://github.com/user-attachments/assets/d75b6dc7-4501-4942-a2b2-1c1e41371a6b" />

**📌Note: This command displays how internal (inside local) IP addresses are translated to public (inside global) IP addresses.** 

---

Even though NAT mappings are **static**, traffic must be generated for translations to appear as active
- The NAT table clearly shows the relationship between **private IPs** and **public IPs**
