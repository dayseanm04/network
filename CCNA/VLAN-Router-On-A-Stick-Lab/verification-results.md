# ✅ VLAN Router On A Stick Lab Verification Results

## Topology For Reference
<img width="677" height="372" alt="Topolgy" src="https://github.com/user-attachments/assets/23709f4e-4dde-49c4-8ce1-47559e75f163" />



<br/>

## 🧩 Lab Overview
| Task | Focus Area | Devices Involved |
|------|-------------|------------------|
| Task 1 | VLAN creation & port assignment | SW1, SW2 |
| Task 2 | Trunk configuration | SW1, SW2 |
| Task 3 | Router-on-a-Stick (ROAS) setup | SW2, R1 |
| Task 4 | Inter-VLAN connectivity testing | PCs |

---

## 🧱 VLAN Verification

### 🔍 Purpose
Verify VLAN creation and correct port assignments on both switches.

### 🧰 Commands Used
```bash
show vlan brief
```

#### SW1 show vlan brief output:
<img width="817" height="232" alt="sw1-show-vlans" src="https://github.com/user-attachments/assets/ebd9f189-3bfa-408b-85b8-b2c07c936571" />


<br/>

#### SW2 show vlan brief output:
<img width="817" height="246" alt="sw2-show-vlans" src="https://github.com/user-attachments/assets/7ee3a17f-2ec7-4241-a4d8-b9ea5bfb1e4c" />


<br/>

### Expected Results

- SW1 shows VLAN 10 (ports f0/1 and f0/2) and VLAN 30 (ports f0/3 and f0/4).
- SW2 shows VLAN 10 (f0/2 and f0/3) and VLAN 20 (f0/1).
- All access ports should be in static access mode and active.

**Note: VLAN30 is displayed here because I created VLAN30 on SW2 so that It could be appart of the active in management domain. Task3**

## 🌉 Trunk Configuration Verification
### 🔍 Purpose
Confirm that trunk links between switches (and to the router) are working.
<br/>

### 🧰 Commands Used
```bash
show interfaces trunk
```

#### SW1 show interfaces trunk: 
<img width="699" height="231" alt="sw1-trunk-int" src="https://github.com/user-attachments/assets/91473c9a-7cf1-4168-85a8-c11120768bb6" />


<br/>

#### SW2 show interfaces trunk: 
<img width="699" height="303" alt="sw2-trunk-int" src="https://github.com/user-attachments/assets/e0fc20da-86c4-42fd-be0d-4635d1fc42e1" />


<br/>

### Expected Results
- SW1 g0/1 trunk is up, allowing VLANs 10 and 30, native VLAN 100.
- SW2 g0/1 trunk is up, allowing VLANs 10 and 30, native VLAN 100.
- SW2 g0/2 trunk is up, allowing VLANs 10, 20, 30, native VLAN 100 (to router).

## Router Subinterfaces Verification
### 🔍 Purpose
Verify that router subinterfaces are configured correctly and active.

### 🧰 Commands Used
```bash
show ip interface brief
show ip route
```

#### show ip interface brief on R1:
<img width="835" height="184" alt="R1-ip-int" src="https://github.com/user-attachments/assets/d82f167f-5b60-46e1-abb7-b7c3c6ad73fd" />


#### show ip route on R1:
<img width="822" height="349" alt="r1-ip-route" src="https://github.com/user-attachments/assets/aa53a2d3-1957-4c07-b934-710b7eba2bd0" />


<br/>

### Expected Results

- Each subinterfaces configured earliar should be up/up with the correct IP address
- The routing table should show the routes to all the vlans

## Inter-VLAN Connectivity Test

### 🔍 Purpose
Verify that PCs in different VLANs can communicate through the router using the **Router-on-a-Stick (ROAS)** configuration.

---

| PC | VLAN | IP Address | Subnet Mask | Default Gateway |
|----|------|-------------|--------------|------------------|
| PC1 | VLAN 10 | 10.0.0.1 | 255.255.255.192 | 10.0.0.62 |
| PC2 | VLAN 10 | 10.0.0.2 | 255.255.255.192 | 10.0.0.62 |
| PC3 | VLAN 20 | 10.0.0.65 | 255.255.255.192 | 10.0.0.126 |
| PC4 | VLAN 30 | 10.0.0.129 | 255.255.255.192 | 10.0.0.190 |
| PC5 | VLAN 30 | 10.0.0.130 | 255.255.255.192 | 10.0.0.190 |

---

### 🧰 Test Steps

1. From each PC, open **Desktop → Command Prompt**.  
2. Ping the **default gateway** to confirm local VLAN connectivity.  
3. Ping **PCs in different VLANs** to verify inter-VLAN routing through the router.  

---

### 📸 Ping Test Results

#### 🖥️ PC1 (VLAN 10)
**Ping Tests:**
- Ping the VLAN10 default gateway `10.0.0.62`  
- Ping PC5 in VLAN 20 `10.0.0.65`  
- Ping PC3 in VLAN 30 `10.0.0.129`

**PC1 VLAN10 ping test:**

<img width="674" height="822" alt="PC1-ping-tests" src="https://github.com/user-attachments/assets/b2c13808-fb0f-41be-a258-add81e581460" />

---

#### 🖥️ PC5 (VLAN 20)
**Ping Tests:**
- Ping the VLAN20 default gateway `10.0.0.126`  
- Ping PC3 in VLAN 30 PC `10.0.0.129`  
- Ping PC6 in VLAN 10 `10.0.0.4`  

**PC5 VLAN20 ping test:**

<img width="738" height="818" alt="PC5-ping-tests" src="https://github.com/user-attachments/assets/a6ca3e37-5138-4313-8151-0efa848d65ac" />

---

#### 🖥️ PC4 (VLAN 30)
**Ping Tests:**
- Ping VLAN30 default gateway `10.0.0.190`  
- Ping PC1 in VLAN 10 `10.0.0.1`  
- Ping PC5 in VLAN 20 `10.0.0.65`  

**PC4 VLAN30 ping test:**

<img width="823" height="784" alt="PC4-ping-tests" src="https://github.com/user-attachments/assets/9409e7c7-1e6f-49ef-a2c4-950d1032a940" />

### ✅ Expected Results
- Each PC can successfully ping its **own VLAN gateway**.  
- PCs from **different VLANs** can ping each other.  
- The **first ping may time out** due to Address Resolution Protocol, but the other pings should suceed.

---

🧑‍💻 *Inter-VLAN connectivity confirmed: All VLANs communicate successfully via Router-on-a-Stick!*
