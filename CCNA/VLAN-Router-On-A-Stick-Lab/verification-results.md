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
<img width="815" height="228" alt="sw1-show-vlans" src="https://github.com/user-attachments/assets/05fbd6df-7f29-4f2f-9997-d269a396fbff" />

<br/>

#### SW2 show vlan brief output:
<img width="813" height="241" alt="sw2-show-vlans" src="https://github.com/user-attachments/assets/c13e9f39-04ae-40b3-9cf8-5f602ccd3e6a" />

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
<img width="693" height="227" alt="sw1-expectedd-trunk-output" src="https://github.com/user-attachments/assets/89d7ed25-4a0d-4d5e-b801-4baa9b524df5" />

<br/>

#### SW2 show interfaces trunk: 
<img width="694" height="300" alt="sw2-trunk-int" src="https://github.com/user-attachments/assets/ffa38c5a-ee29-423a-913f-d4239daf7506" />

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
<img width="834" height="184" alt="R1-ip-int" src="https://github.com/user-attachments/assets/8f23501a-3840-4527-8d0e-04ac28d5b937" />

#### show ip route on R1:
<img width="818" height="345" alt="r1-ip-route" src="https://github.com/user-attachments/assets/3440046a-38d3-4821-a311-f79e51414789" />

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
>  <img width="748" height="911" alt="PC1-ping-tests" src="https://github.com/user-attachments/assets/531ae0b7-c2b0-4417-a564-7da9293d7fd4" />

---

#### 🖥️ PC5 (VLAN 20)
**Ping Tests:**
- Ping the VLAN20 default gateway `10.0.0.126`  
- Ping PC3 in VLAN 30 PC `10.0.0.129`  
- Ping PC6 in VLAN 10 `10.0.0.4`  

**PC5 VLAN20 ping test:**
> <img width="819" height="913" alt="PC5-ping-tests" src="https://github.com/user-attachments/assets/949efb74-a00d-4b89-9f91-91fb99816f7b" />

---

#### 🖥️ PC4 (VLAN 30)
**Ping Tests:**
- Ping VLAN30 default gateway `10.0.0.190`  
- Ping PC1 in VLAN 10 `10.0.0.1`  
- Ping PC5 in VLAN 20 `10.0.0.65`  

**PC4 VLAN30 ping test:**
> <img width="953" height="910" alt="PC4-ping-tests" src="https://github.com/user-attachments/assets/37e1d91d-3af5-4fdc-91a3-f1fd659aad3b" />

### ✅ Expected Results
- Each PC can successfully ping its **own VLAN gateway**.  
- PCs from **different VLANs** can ping each other.  
- The **first ping may time out** due to Address Resolution Protocol, but the other pings should suceed.

---

🧑‍💻 *Inter-VLAN connectivity confirmed — All VLANs communicate successfully via Router-on-a-Stick!*
