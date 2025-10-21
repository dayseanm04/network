# 🧭 Static Route Troubleshooting Lab

## Topology For Reference
<img width="682" height="275" alt="TFR" src="https://github.com/user-attachments/assets/b06669f8-b20c-4d9d-98e8-f4abeefac4a9" />

---

## 🎯 Objective
The goal of this lab is to **find and fix static routing misconfigurations** between three routers so that **PC1 and PC2 can successfully communicate with each other**.  
Verify IP addressing, routing tables, and next-hop configurations to restore end-to-end connectivity.

---

## 🧠 Lab Summary
In this lab, PC1 and PC2 were unable to ping each other due to incorrect static route and interface configurations on multiple routers.  
By checking interface IPs, reviewing routing tables, and correcting next-hop values, full communication was restored.

✅ **Key Results:**
- Routing loop fixed  
- Configured the correct static routes  
- Successful pings between PC1 and PC2  

---

## 🧩 Network Overview
**Devices:**
- 3 Cisco cisco 2911 Routers (R1, R2, R3)
- 2 PCs (PC1 and PC2)
- 2 Catalyst WS-C2960-24TT Switches (SW1 and SW2)

**Goal:** Ensure all routers have correct static routes so **PC1 & PC2** can successfully communicate with each other.

---

## 💡 Takeaways
- Always verify **next-hop IPs** when configuring static routes.  
- Incorrect exit interfaces can cause **routing loops**.  
- Use **simulation mode** to trace ICMP packets and identify issues.  
- Systematic troubleshooting saves time and avoids reconfiguration errors.
