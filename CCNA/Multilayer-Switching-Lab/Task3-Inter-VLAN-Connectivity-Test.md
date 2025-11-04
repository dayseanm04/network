# 🧩 Multilayer Switching Lab

## Task 3 Inter-VLAN Connectivity Test 🌐
This document records the results of **inter-VLAN connectivity tests** conducted after configuring SVIs on the multilayer switch (SW2).

---
## Topology For Reference
<img width="675" height="337" alt="Topology" src="https://github.com/user-attachments/assets/8fe195ed-f8f0-4bbb-8e33-8be947c5463a" />


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

<img width="741" height="403" alt="PC1-PC3" src="https://github.com/user-attachments/assets/50642b8d-58d1-4766-a844-d867fdfc1966" />

---

### 🔹 VLAN 10 ↔ VLAN 20
**Test:** PC1 (VLAN10) → PC5 (VLAN20)  
**Expected Result:** ✅ Success

<img width="746" height="362" alt="PC1-PC5" src="https://github.com/user-attachments/assets/c4152efc-c9dd-495d-b155-f4bdef16fd6f" />


---

### 🔹 VLAN 30 ↔ VLAN 10
**Test:** PC4 (VLAN30) → PC6 (VLAN10)  
**Expected Result:** ✅ Success 

<img width="749" height="369" alt="PC4-PC6" src="https://github.com/user-attachments/assets/f0991344-0165-4d47-8862-1abf2b374faf" />


--

### 🔹 VLAN 20 ↔ VLAN 10
**Test:** PC5 (VLAN20) → PC2 (VLAN10)  
**Expected Result:** ✅ Success

<img width="753" height="380" alt="PC5-PC2" src="https://github.com/user-attachments/assets/7c4339f5-2fa4-4e5e-b5bc-86d439f6fab4" />


---

### 🔹 VLAN 10 ↔ VLAN 20 (Reverse)
**Test:** PC6 (VLAN10) → PC5 (VLAN20)  
**Expected Result:** ✅ Success

<img width="741" height="409" alt="PC6-PC5" src="https://github.com/user-attachments/assets/0fd3dd4a-ccbb-45d2-b256-446c4ba7cf2d" />

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
