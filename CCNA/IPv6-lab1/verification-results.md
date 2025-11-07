# ✅ IPv6 Configuration Verification

## 🧩 Overview
This document verifies the successful configuration of IPv6 on the router and end devices.  
It includes evidence of IPv6 routing, interface addressing, and end-to-end connectivity between PCs using both IPv4 and IPv6.

---

## 🔹 Router Interface Verification
**Objective:** Verify that all router interfaces have the correct IPv6 addresses and are operational.

**Verification Command Used:**  
```bash
show ipv6 interface brief
```

**Expected output ✅:**

<img width="635" height="233" alt="R1-show-ipv6-int" src="https://github.com/user-attachments/assets/9d0ab0bc-c0cf-43a4-b668-8a377c39ebc4" />



**Expected Results:**
| Interface | IPv6 Address | Status |
|------------|---------------|---------|
| G0/0 | 2001:DB8:0:1::1/64 | up/up |
| G0/1 | 2001:DB8:0:2::1/64 | up/up |
| G0/2 | 2001:DB8:0:3::1/64 | up/up |


---

## 🔹 Router Running Configuration
**Objective:** Confirm the correct IPv6 addresses are configured on each interface.

**Verification Command Used:**  
```bash
show running-config | section interface
```

**Expected output ✅:**

<img width="484" height="348" alt="R1-running-config" src="https://github.com/user-attachments/assets/f42f5a8e-2b43-4a7a-8c5c-270fd048c5d4" />

---

## 🔹 PC IPv6 Configuration Verification
**Objective:** Verify that all PCs have the correct IPv6 address and default gateway settings.

**PC1 IP config:** 

<img width="745" height="420" alt="PC1-IPC" src="https://github.com/user-attachments/assets/42d70971-cd3c-4989-840d-cb3d8bc20ae9" />


**PC2 IP config:**

<img width="746" height="343" alt="PC2-IPC" src="https://github.com/user-attachments/assets/4f32e37c-c116-4c17-8017-5134762230dd" />


**PC3 IP config:** <br/>

<img width="749" height="350" alt="PC3-IPC" src="https://github.com/user-attachments/assets/73ea93bf-4b6e-48e3-9af5-815000e3b571" />

**Expected results:**
| PC | IPv6 Address | Default Gateway |
|----|---------------|----------------|
| PC1 | 2001:DB8:0:1::2/64 | 2001:DB8:0:1::1 |
| PC2 | 2001:DB8:0:2::2/64 | 2001:DB8:0:2::1 |
| PC3 | 2001:DB8:0:3::2/64 | 2001:DB8:0:3::1 |

---

## 🔹 IPv4 Connectivity Test
**Objective:** Verify that IPv4 connectivity is still functional after enabling IPv6 (dual-stack).
**Verification Method:** Ping tests between PCs using their IPv4 addresses.

## 🧾 PC IP addresses

| PC  | IPv4 Address   | IPv4 Default Gateway | IPv6 Address           | IPv6 Default Gateway  |
|-----|----------------|----------------------|------------------------|-----------------------|
| PC1 | 192.168.1.2    | 192.168.1.1          | 2001:DB8:0:1::2/64     | 2001:DB8:0:1::1       |
| PC2 | 192.168.2.2    | 192.168.2.1          | 2001:DB8:0:2::2/64     | 2001:DB8:0:2::1       |
| PC3 | 192.168.3.2    | 192.168.3.1          | 2001:DB8:0:3::2/64     | 2001:DB8:0:3::1       |

---

**PC1 ipv4 ping test:**

<img width="739" height="620" alt="pc1-ipv4-pt" src="https://github.com/user-attachments/assets/03e92199-bfbb-44db-a383-16d2049f0fb8" />


**PC2 ipv4 ping test:**

<img width="740" height="624" alt="pc2-ipv4-pt" src="https://github.com/user-attachments/assets/e293a285-66f1-43c7-9dc0-85f9812d7546" />

**PC3 ipv4 ping test:**

<img width="737" height="615" alt="pc3-ipv4-pt" src="https://github.com/user-attachments/assets/93f57249-1de9-445b-820d-af84109cdc4a" />


✅ **Expected results:** All pings succeed using IPv4.

---

## 🔹 IPv6 Connectivity Test
**Objective:** Confirm successful IPv6 connectivity between PCs using the configured IPv6 addresses.
**Verification Method:** Ping between PCs using their IPv6 addresses.

**PC1 ipv6 ping test:** <br/>
<img width="735" height="615" alt="PC1-ipv6-ping" src="https://github.com/user-attachments/assets/f37cfe8f-ab9c-47f9-adcd-6a5049d97174" />
<br/>

**PC2 ipv6 ping test:** <br/>
<img width="745" height="623" alt="PC2-ipv6-ping" src="https://github.com/user-attachments/assets/bfd37cee-f2c8-4ebf-8d7c-1f25a08146d2" /> <br/>

**PC3 ipv6 ping test:** <br/>
<img width="738" height="656" alt="PC3-ipv6-ping" src="https://github.com/user-attachments/assets/978fc383-9bfb-4a13-9bb1-b267021c6483" /> <br/>


✅ **Expected results:**  
- All PCs can ping each other’s IPv6 addresses.  
- Dual-stack verified (IPv4 and IPv6 both functional).
