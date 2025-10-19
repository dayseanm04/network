# verification & results

This file documents the **verification &  results for the entire Static Route Lab (Task 1 & Task 2)**.  

---

## 🧩 Lab Summary
| **Task** | **Description** | **Goal** |
|-----------|-----------------|-----------|
| **Task 1** | Configure router interfaces and PC IP settings | Establish basic Layer 3 connectivity between routers |
| **Task 2** | Configure static routes on all routers | Enable full end-to-end communication between PC1 and PC2 |

---

## 🖥️ Router Verifications

### 🚀 R1 Verification

#### 🔌 Interface Status
**Command:**
```bash
show ip int brief
```

**Note: show ip in brief is the shortcut of show ip interface brief**

**Expected Output ✅**
<img width="815" height="135" alt="R1-int" src="https://github.com/user-attachments/assets/9e78767b-ca9d-4279-9823-8d93ea6aa9c3" />

#### 🧭 Routing Table
**Command:**
```bash
show ip route
```

**Expected Output ✅**
<img width="809" height="338" alt="R1 RT" src="https://github.com/user-attachments/assets/ee7f4f7a-2366-4e55-802a-4b6d622f5e07" />


---

### 🔁 R2 Verification

#### 🔌 Interface Status
**Command:**
```bash
show ip int brief
```

**Expected Output ✅**
<img width="809" height="131" alt="R2-int" src="https://github.com/user-attachments/assets/a414def4-0286-4fa1-8486-4916f770a477" />

#### 🧭 Routing Table
**Command:**
```bash
show ip route
```

**Expected Output ✅**
<img width="809" height="361" alt="R2-RT" src="https://github.com/user-attachments/assets/0b5ef031-3489-4572-81c0-eecc5f789b89" />


---

### 🔄 R3 Verification

#### 🔌 Interface Status
**Command:**
```bash
show ip int brief
```

**Expected Output ✅**
<img width="806" height="132" alt="R3-int" src="https://github.com/user-attachments/assets/c769a6c7-dc3a-4583-9b1c-721fd88409ac" />

#### 🧭 Routing Table
**Command:**
```bash
show ip route
```

**Expected Output ✅**
<img width="729" height="374" alt="R3-RT" src="https://github.com/user-attachments/assets/44cd65fa-b831-4927-85e9-483fd36d3e83" />

---

## 💻 PC Verifications

### 🧠 PC1 Configuration
**Command:**  
`ipconfig`

**Expected Output ✅**
<img width="740" height="348" alt="PC1-IP-config" src="https://github.com/user-attachments/assets/faa6fc3d-d45e-4ef3-aeae-a591c40570af" />

### 🧠 PC2 Configuration
**Command:**  
`ipconfig`

**Expected Output ✅**
<img width="735" height="354" alt="PC2-IP-config" src="https://github.com/user-attachments/assets/5aec03f4-edc7-48e2-994c-8bd7c430abd6" />

---

## 🔍 Connectivity Verification
###  Ping Tests Between PCs

#### PC1 => PC2
**Expected Output ✅**
<img width="742" height="336" alt="PC1-PC2" src="https://github.com/user-attachments/assets/938e95ba-a674-49be-842e-715a6041bc73" />

#### PC2 => PC1
**Expected Output ✅**
<img width="738" height="363" alt="PC2-PC1" src="https://github.com/user-attachments/assets/9107652c-51c3-4e4e-9d0a-c437dda25432" />


---

## 🧾 Summary of Results

✅ **Interfaces:** All router interfaces are up and correct they have the correct IP addresses assigned.  
✅ **Routing Tables:** All static routes are correctly configured.  
✅ **PCs:** All PCs have the correct IP addresses and gateways.  
✅ **Ping Tests:** Successful communication between PC1 and PC2

---

## ✍️ Author
**Name:** *Daysean Mensah*  
**Course:** *CCNA Studies*  
**Date:** *10/19/2025*
