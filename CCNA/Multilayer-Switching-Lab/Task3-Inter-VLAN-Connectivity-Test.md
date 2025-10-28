# 🧩 Multilayer Switching Lab

## Task 3 Inter-VLAN Connectivity Test 🌐
This document records the results of **inter-VLAN connectivity tests** conducted after configuring SVIs on the multilayer switch (SW2).

---
## Topology For Reference
<img width="672" height="333" alt="topology" src="https://github.com/user-attachments/assets/f269aa76-a65d-409d-a42e-8e9da18e6c7b" />

---

## 🧩 Objective
Verify that hosts in different VLANs can communicate with each other through the multilayer switch using **inter-VLAN routing**.

---

## 🖥️ Device Information

| Device | VLAN | IP Address |
|---------|------|-------------|
| PC1 | 10 | 10.0.0.1/26 |
| PC2 | 10 | 10.0.0.2/26 |
| PC3 | 30 | 10.0.0.129/26 |
| PC4 | 30 | 10.0.0.130/26 |
| PC5 | 20 | 10.0.0.65/26 |
| PC6 | 10 | 10.0.0.4/26 |
| PC7 | 10 | 10.0.0.3/26 |

---

## 🧠 Inter-VLAN Ping Tests

### 🔹 VLAN 10 ↔ VLAN 30
**Test:** PC1 (VLAN10) → PC3 (VLAN30)  
**Expected Result:** ✅ Success

<img width="742" height="404" alt="PC1-PC3" src="https://github.com/user-attachments/assets/c391c5a7-5fff-4b5c-ba2a-91dd026f2a54" />

---

### 🔹 VLAN 10 ↔ VLAN 20
**Test:** PC1 (VLAN10) → PC5 (VLAN20)  
**Expected Result:** ✅ Success

<img width="752" height="366" alt="PC1-PC5" src="https://github.com/user-attachments/assets/bbba47f1-ee48-444e-981d-3e8b4a4532fb" />

---

### 🔹 VLAN 30 ↔ VLAN 10
**Test:** PC4 (VLAN30) → PC6 (VLAN10)  
**Expected Result:** ✅ Success 

<img width="756" height="372" alt="PC4-PC6" src="https://github.com/user-attachments/assets/d783b4d8-79e6-4e9a-998a-c4c1d2e54ea1" />

--

### 🔹 VLAN 20 ↔ VLAN 10
**Test:** PC5 (VLAN20) → PC2 (VLAN10)  
**Expected Result:** ✅ Success

<img width="757" height="384" alt="PC5-PC2" src="https://github.com/user-attachments/assets/98d64982-eb68-4424-93aa-d507c0fbeedd" />

---

### 🔹 VLAN 10 ↔ VLAN 20 (Reverse)
**Test:** PC6 (VLAN10) → PC5 (VLAN20)  
**Expected Result:** ✅ Success

<img width="747" height="414" alt="PC6-PC5" src="https://github.com/user-attachments/assets/5b9f7ded-c43a-4f4c-a391-2dee28809633" />

---

## ✅ Summary of Results

| Source | Destination | VLANs | Result |
|---------|--------------|--------|----------|
| PC1 | PC3 | 10 ↔ 30 | ✅ Success |
| PC1 | PC5 | 10 ↔ 20 | ✅ Success |
| PC4 | PC6 | 30 ↔ 10 | ✅ Success |
| PC5 | PC2 | 20 ↔ 10 | ✅ Success |
| PC6 | PC5 | 10 ↔ 20 | ✅ Success |

All inter-VLAN pings were **successful**, confirming that:
- SVIs are configured correctly  
- IP routing is enabled on SW2  
- Hosts can communicate across VLAN boundaries  
