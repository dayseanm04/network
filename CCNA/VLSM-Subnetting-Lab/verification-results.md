# ✅ Verification Results

## 🛠️ Task 2: Router Interface Configuration Verification

Verify that each router interface has the **correct IP address** (last usable of each subnet) and is **up/up**.  

### 1️⃣ R1 Interface Verification
```bash
show ip interface brief
```

**Expected Output ✅**
<img width="813" height="146" alt="R1-show-int" src="https://github.com/user-attachments/assets/25989618-796e-41ac-b7ae-50355cd47579" />



### 2️⃣ R2 Interface Verification
```bash
show ip interface brief
```

**Expected Output ✅**
<img width="790" height="163" alt="R2-ip-int" src="https://github.com/user-attachments/assets/94badb4a-0d6f-4331-b37b-686a8d54ef39" />


---

## 🛠️ Task 3: PC Configuration Verification

Verify that each PC has the **correct IP address** and **default gateway** assigned.

| PC   | LAN  | IP Address      | Subnet Mask        | Default Gateway  | Status |
|------|------|----------------|------------------|----------------|--------|
| PC1  | LAN1 | 192.168.5.129  | 255.255.255.192  | 192.168.5.190  | ✅      |
| PC2  | LAN2 | 192.168.5.1    | 255.255.255.128  | 192.168.5.126  | ✅      |
| PC3  | LAN3 | 192.168.5.193  | 255.255.255.224  | 192.168.5.222  | ✅      |
| PC4  | LAN4 | 192.168.5.225  | 255.255.255.240  | 192.168.5.238  | ✅      |

---

## 🛣️ Task 4: Static Route Verification
Verify that **static routes** are correctly configured on each router.

### 3️⃣ R1 Route Verification
```bash
show ip route
```

#### Expected Output ✅
<img width="722" height="422" alt="R1-route" src="https://github.com/user-attachments/assets/963bae68-34d8-4ade-b0bf-5437530d0a2a" />



### 4️⃣ R2 Route Verification
```bash
show ip route
```

#### Expected Output ✅
<img width="714" height="417" alt="R2-route" src="https://github.com/user-attachments/assets/3f43dcb7-0c44-4df7-9bf5-4ef2cd274271" />


---

## 📶 Ping Test Verification

Verify connectivity between PCs in different LANs.  

## 🖼️ Ping Test Screenshots

Insert your ping test screenshots here to visually confirm connectivity between all PCs.

### PC1 Ping Tests
- **PC1 → PC2 (192.168.5.1)**
<img width="740" height="390" alt="PC1-PC2" src="https://github.com/user-attachments/assets/1dac8278-bb21-4a56-9173-25448f8637ae" />



- **PC1 → PC3 (192.168.5.193)**  

<img width="744" height="359" alt="PC1-PC3" src="https://github.com/user-attachments/assets/0eaf8148-be06-42ea-95b0-ed48d625bcc0" />

 
- **PC1 → PC4 (192.168.5.225)**  

<img width="743" height="356" alt="PC1-PC4" src="https://github.com/user-attachments/assets/4c29bad5-988f-47d8-a83e-d95ce1a10ee9" />

  
---

### PC2 Ping Tests
- **PC2 → PC1 (192.168.5.129)**
<img width="749" height="328" alt="PC2-PC1" src="https://github.com/user-attachments/assets/e0f4e8b9-1c2c-4b28-a8c8-afbf30447ebd" />

 
- **PC2 → PC3 (192.168.5.193)**  
<img width="743" height="362" alt="PC2-PC3" src="https://github.com/user-attachments/assets/d639e897-4b0f-4e41-b91e-88e5c50171eb" />



- **PC2 → PC4 (192.168.5.225)**  
<img width="743" height="365" alt="PC2-PC4" src="https://github.com/user-attachments/assets/78eaac02-5f1e-4906-95c8-dcf019198db2" />



---

### PC3 Ping Tests
- **PC3 → PC1 (192.168.5.129)**  
<img width="735" height="366" alt="PC3-PC1" src="https://github.com/user-attachments/assets/55c919f4-ba20-4a7a-a6e4-5fc535b6c518" />



- **PC3 → PC2 (192.168.5.1)**  
<img width="744" height="376" alt="PC3-PC2" src="https://github.com/user-attachments/assets/01863470-bac3-4423-a0b2-ee7191486278" />

 

- **PC3 → PC4 (192.168.5.225)**  
<img width="739" height="364" alt="PC3-PC4" src="https://github.com/user-attachments/assets/691fdfbc-f68e-474a-8ab3-100cb55dc1f4" />


---

### PC4 Ping Tests
- **PC4 → PC1 (192.168.5.129)**  
<img width="746" height="364" alt="PC4-PC1" src="https://github.com/user-attachments/assets/8e335ce4-7e98-4e12-a5a1-3316671f2395" />


- **PC4 → PC2 (192.168.5.1)**  
<img width="745" height="362" alt="PC4-PC2" src="https://github.com/user-attachments/assets/c24f1167-df2a-46f7-8a4c-a72c9abac9e5" />

  
- **PC4 → PC3 (192.168.5.193)**  
<img width="743" height="362" alt="PC4-PC3" src="https://github.com/user-attachments/assets/97b1568b-4b43-4013-bce2-4aaff0987f3c" />
