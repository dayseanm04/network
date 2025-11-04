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
**PC1 → PC2 (192.168.5.1)**
<img width="740" height="393" alt="PC1-PC2" src="https://github.com/user-attachments/assets/61dc9eb5-0791-4ef6-b4a7-eb988f9483e7" />


**PC1 → PC3 (192.168.5.193)**  
<img width="738" height="359" alt="PC1-PC3" src="https://github.com/user-attachments/assets/f53b9c5d-28f0-43e0-be16-b8f6bedd6d89" />

 **PC1 → PC4 (192.168.5.225)**  
<img width="740" height="359" alt="PC1-PC4" src="https://github.com/user-attachments/assets/e9fae396-f074-4f8a-b069-f9c87cbd7605" />


---

### PC2 Ping Tests

**PC2 → PC1 (192.168.5.129)**
<img width="749" height="329" alt="PC2-PC1" src="https://github.com/user-attachments/assets/ef271d23-aa83-4911-83c5-aaeff7052b8f" />


**PC2 → PC3 (192.168.5.193)**  
<img width="730" height="361" alt="PC2-PC3" src="https://github.com/user-attachments/assets/ddb098ce-c63a-4a90-a853-68cae224f299" />




**PC2 → PC4 (192.168.5.225)**  
<img width="730" height="363" alt="PC2-PC4" src="https://github.com/user-attachments/assets/c690b799-872d-43b6-b9a3-6219e79932de" />


---

### PC3 Ping Tests

**PC3 → PC1 (192.168.5.129)**  
<img width="735" height="367" alt="PC3-PC1" src="https://github.com/user-attachments/assets/8fb7ce7b-91f7-4818-b1ba-7d16e0735f89" />


**PC3 → PC2 (192.168.5.1)**  
<img width="731" height="373" alt="PC3-PC2" src="https://github.com/user-attachments/assets/0e5c1347-cae5-41d9-8545-81cef4763047" />


**PC3 → PC4 (192.168.5.225)**  
<img width="735" height="359" alt="PC3-PC4" src="https://github.com/user-attachments/assets/ead1b3fb-835a-4a7c-83b2-173558fc1323" />


---

### PC4 Ping Tests

**PC4 → PC1 (192.168.5.129)**  
<img width="743" height="364" alt="PC4-PC1" src="https://github.com/user-attachments/assets/90c32c0a-bf88-423e-af37-72233eb3875a" />



**PC4 → PC2 (192.168.5.1)**  
<img width="737" height="361" alt="PC4-PC2" src="https://github.com/user-attachments/assets/7d584880-b1f0-4379-a334-54fd8725b997" />


  
**PC4 → PC3 (192.168.5.193)**  
<img width="736" height="360" alt="PC4-PC3" src="https://github.com/user-attachments/assets/387d757e-adeb-4119-b0c2-d9aedc12ca12" />
