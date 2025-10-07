# 🔍 Verification and Results – VLAN Intro Lab

## 📘 Overview
This document shows the results and verification steps for the **VLAN Intro Lab**.  
Each section includes screenshots demonstrating successful pings and connectivity tests for the configured VLANs and router interfaces.

---

## 🖥️ PC IP addresses Table

| PC Name | VLAN  | IPv4 Address   | Subnet Mask       | Default Gateway |
|---------|-------|----------------|-----------------|----------------|
| PC1     | 10    | 10.0.0.1      | 255.255.255.192 | 10.0.0.62      |
| PC2     | 10    | 10.0.0.2      | 255.255.255.192 | 10.0.0.62      |
| PC3     | 20    | 10.0.0.65     | 255.255.255.192 | 10.0.0.126     |
| PC4     | 20    | 10.0.0.66     | 255.255.255.192 | 10.0.0.126     |
| PC5     | 30    | 10.0.0.129    | 255.255.255.192 | 10.0.0.190     |
| PC6     | 30    | 10.0.0.130    | 255.255.255.192 | 10.0.0.190     |

---

## 1️⃣ Ping Within Same VLAN
**Objective:** Verify that PCs in the same VLAN can communicate with each other.  
This confirms that VLAN membership and access port configurations are correct.

### PC1 → PC2 (VLAN 10)<br/>
<img width="598" height="431" alt="pc1-ping" src="https://github.com/user-attachments/assets/27b77e37-4911-4388-a954-5096d885852a" />


### PC3 → PC4 (VLAN 20)<br/>
<img width="634" height="433" alt="pc3-ping" src="https://github.com/user-attachments/assets/4b624dd1-d0c9-4f64-bc47-9fa64a9ec292" />


### PC5 → PC6 (VLAN 30)<br/>
<img width="619" height="369" alt="pc5-ping" src="https://github.com/user-attachments/assets/ab1a4d2a-4937-4093-9314-74586d133826" />


---

## 2️⃣ Ping Default Gateway
**Objective:** Confirm that each PC can reach its VLAN’s default gateway (router interface).  
This validates the PC’s IP, subnet mask, and default gateway settings.

### PC1 → 10.0.0.62 <br/>
<img width="599" height="366" alt="pc1-ping-df" src="https://github.com/user-attachments/assets/caa66645-3936-4a6b-90c5-676570a54777" />

### PC3 → 10.0.0.126 <br/>
<img width="616" height="407" alt="pc3-ping-int" src="https://github.com/user-attachments/assets/50280c89-170b-40d7-a0bd-47c6dc445690" />


### PC5 → 10.0.0.190
<img width="613" height="366" alt="pc5-ping-int" src="https://github.com/user-attachments/assets/88eb06aa-908e-4309-802a-2d85016e0824" />


---

## 3️⃣ Ping Between VLANs
**Objective:** Test inter-VLAN routing by sending pings between devices on different VLANs.  
Successful results indicate that the router is correctly configured for inter-VLAN communication.

### PC1 (VLAN 10) → PC3 (VLAN 20) <br/>
<img width="607" height="422" alt="pc1-ping-pc3" src="https://github.com/user-attachments/assets/792372fe-bb4f-463f-be9f-ed07b15710d7" />

### PC2 (VLAN 10) → PC5 (VLAN 30) <br/>
<img width="626" height="400" alt="pc2-ping-pc5" src="https://github.com/user-attachments/assets/b651c750-ec5e-47df-86a9-4d789198246c" />


### PC4 (VLAN 20) → PC6 (VLAN 30) <br/>
<img width="613" height="397" alt="pc4-ping-pc6" src="https://github.com/user-attachments/assets/0d48cd07-3ac8-49dc-956a-0cc2fd94d7f2" />


---

## 4️⃣ Router Interface Verification
**Objective:** Verify that all router interfaces are up and have correct IP assignments.  
This ensures each VLAN gateway is properly configured and operational.

**Command Used:**
```bash
show ip interface brief
```
<img width="821" height="132" alt="show-r1-int" src="https://github.com/user-attachments/assets/b2a9f49b-3463-4cc0-b9b4-1df978fb8340" />


## 5️⃣ VLAN Verification

**Command Used:**
```bash
show ip vlan brief
```

<img width="766" height="237" alt="show-vlan" src="https://github.com/user-attachments/assets/ff12a686-ee09-43da-a3f2-ae6a90247115" />
