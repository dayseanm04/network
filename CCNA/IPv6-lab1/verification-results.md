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
`show running-config | section interface`

<img width="485" height="347" alt="R1-running-config" src="https://github.com/user-attachments/assets/ee1b8a7f-6eed-47fa-8f53-e1ccc2ab62e1" />

---

## 🔹 PC IPv6 Configuration Verification
**Objective:** Verify that all PCs have the correct IPv6 address and default gateway settings.

**PC1 IP config:** <br/>
<img width="744" height="418" alt="pc1-ipc" src="https://github.com/user-attachments/assets/0946f346-5687-4bb5-99e9-bdfb606c149b" /> <br/>

**PC2 IP config:**
<img width="745" height="340" alt="pc2-ipc" src="https://github.com/user-attachments/assets/126a1ebd-7f2e-42dd-8e20-14830441d8ab" /> <br/>


**PC3 IP config:** <br/>
<img width="745" height="347" alt="pc3-ipc" src="https://github.com/user-attachments/assets/2084c00c-bae6-4d87-b587-f264e786ad42" /> <br/>

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

**PC1 ipv4 ping test:** <br/>
<img width="734" height="612" alt="pc1-ipv4-pt" src="https://github.com/user-attachments/assets/61833cf0-fe0e-41db-be4f-e50847fcd71b" /> <br/>

**PC2 ipv4 ping test:** <br/>
<img width="735" height="622" alt="pc2-ipv4-pt" src="https://github.com/user-attachments/assets/3750e285-6056-41c6-8daf-1242cfc13941" /> <br/>

**PC3 ipv4 ping test:** <br/>
<img width="741" height="616" alt="pc3-ipv4-pt" src="https://github.com/user-attachments/assets/a49d2c33-9435-49da-a488-abdb89f5a560" /> <br/>


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
