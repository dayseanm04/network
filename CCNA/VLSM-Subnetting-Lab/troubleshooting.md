# 🛠️ Troubleshooting Connectivity Issues Due to Misconfigured Static Routes and PC IP misconfig

## 🧩 Issue Summary

- **Problem:** PC4 could not ping PC1 and PC2.  
- **Observation:** Using **Simulation Mode**, the ICMP packets reached **R1** but stopped there.  

---

## 🗺️ Static Route Summary

Below is a summary of all the **correct static routes** configured after troubleshooting:

| Destination Network | Subnet Mask        | Next Hop IP     | Description |
|---------------------|--------------------|-----------------|--------------|
| 192.168.5.0/25      | 255.255.255.128    | 192.168.5.242   | Route from R1 to LAN2 via R2 |
| 192.168.5.128/26    | 255.255.255.192    | 192.168.5.242   | Route from R1 to LAN1 via R2 |
| 192.168.5.192/27    | 255.255.255.224    | 192.168.5.241   | Route from R2 to LAN3 via R1 |
| 192.168.5.224/28    | 255.255.255.240    | 192.168.5.241   | Route from R2 to LAN4 via R1 |

🧭 **Point-to-Point Network:**  
- **Network:** 192.168.5.240/30  
- **R1 Interface IP:** 192.168.5.241  
- **R2 Interface IP:** 192.168.5.242

---

## 🔍 Step 1: Troubleshoot R1 Routes

**Command used:**
```bash
show ip route
```

**Problem found:**

<img width="844" height="416" alt="misconfigured-route" src="https://github.com/user-attachments/assets/add397dd-e3bd-4886-8c94-a2058e8efa00" />

| Misconfiguration | Incorrect Value                  | Notes |
|-----------------|---------------------------------|-------|
| Point-to-Point IP | 192.168.5.240                   | Should be 192.168.5.242 |
| Static Route to LAN3/LAN4 | Wrong subnet mask / IP in route | Prevented packets from reaching LAN3/LAN4 |

Problem: the next hop to LAN3 and LAN4 is suppose to be 192.168.5.242 not 192.168.5.240. And also 192.16.8.5.224/27 (LAN4) because LAN3 uses /27 and LAN4 uses /28

**Fix applied:**

1. Remove incorrect routes:
```bash
no ip route 192.168.5.224 255.255.255.240 192.168.4.240
no ip route 192.168.5.224 255.255.255.224 192.168.4.240
```

2. Configure correct static route:
```bash
ip route 192.168.5.224 255.255.255.240 192.168.5.242
```

### Verify the route
```bash
show ip route
```

<img width="899" height="386" alt="R1-route-fixed" src="https://github.com/user-attachments/assets/d820429f-1303-4730-b48a-7324fae3829b" />


✅ After this fix **PC4 could ping PC1 and PC2**. 

---

## 🔍 Step 2: Troubleshoot PC2

## 🗂️ Subnets

| LAN  | Subnet (Prefix)      | Subnet Mask        | Default Gateway (Router) | PC (Assigned IP: first usable) |
|------|--------------------|--------------------|--------------------------|----------------------------------|
| LAN2 | 192.168.5.0/25     | 255.255.255.128    | 192.168.5.126            | PC2: 192.168.5.1                |
| LAN1 | 192.168.5.128/26   | 255.255.255.192    | 192.168.5.190            | PC1: 192.168.5.129              |
| LAN3 | 192.168.5.192/27   | 255.255.255.224    | 192.168.5.222            | PC3: 192.168.5.193              |
| LAN4 | 192.168.5.224/28   | 255.255.255.240    | 192.168.5.238            | PC4: 192.168.5.225              |
| P2P  | 192.168.5.240/30   | 255.255.255.252    | R1: 192.168.5.241 / R2: 192.168.5.242 | (Point-to-Point link) |

---

**Misconfiguration:**
<img width="729" height="313" alt="PC2-micongi" src="https://github.com/user-attachments/assets/2d56bc2d-3cb6-4558-8c04-d4a819bd1300" />

Note: 192.168.5.190 is the default gateway for LAN1, PC2 is in LAN2. And also 255.255.255.192 is LAN1 subnet mask.

**Fix applied:**
<br/>
<img width="751" height="317" alt="PC2-fixed" src="https://github.com/user-attachments/assets/bd781731-f785-4e18-87aa-bd1a0a3fce26" />

Fix: 
- I changed PC2 default gateway to LAN2 gateway (192.168.5.126)
- I also changed PC2 subnet mask to 255.255.255.128 (/25)

✅ After this fix, **PC4 could ping PC2 successfully**.  

## 🔍 Step 3: Troubleshoot PC1

**Misconfiguration:**
<img width="737" height="327" alt="PC1-misconfig" src="https://github.com/user-attachments/assets/69a3c314-872d-4383-bd49-cd760ed14251" />
<br/>
Note: 192.168.5.126 is the default gateway for LAN2, PC1 is in LAN1


**Fix applied:**
<br/>
<img width="747" height="318" alt="PC1-fix" src="https://github.com/user-attachments/assets/79ded6e7-5c63-4c21-bbd0-f1d3e8b8ecc0" />

I changed PC1 default gateway to 192.168.5.190 LAN1 default gateway 

✅ After this fix, PC1 works correctly and **can communicate with all other PCs**.  

## 🎯 Summary

- Misconfigurations on **R1 static routes** and **PC IP/gateway settings** caused connectivity issues.  
- Fixing the **point-to-point IP**, **subnet masks**, and **default gateways** resolved all problems.  
- All PCs can now successfully ping each other. ✅

---

💡 **Tip:** Always verify:
- Router interface IPs and subnet masks  
- Static routes and next-hop IPs  
- PC IP addresses, subnet masks, and default gateways  
- Connectivity using ping before considering the network fully functional
