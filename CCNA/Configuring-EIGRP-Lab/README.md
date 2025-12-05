# 🚀 Configuring EIGRP Lab

This lab focuses on configuring Enhanced Interior Gateway Routing Protocol (EIGRP) across four routers.
I will configure hostnames, interfaces, loopbacks, routing, passive interfaces, and unequal-cost load balancing. 
The goal is to understand how EIGRP forms adjacencies, advertises networks, and selects routes based on metrics.

## Topology For reference

<img width="599" height="320" alt="topology" src="https://github.com/user-attachments/assets/e146f7b8-7977-42ce-8984-0c92d4d92d0d" />

## 📘 Lab Summary

In this lab, each router is configured with correct interface IPs and a unique loopback address. EIGRP Autonomous System 100 is enabled on all routers, with auto-summary disabled and passive interfaces applied where appropriate. After full adjacency is formed, R1 is configured to perform **unequal-cost load balancing** toward the 192.168.4.0/24 network using EIGRP’s *variance* feature.
<br/>
I will observe EIGRP neighbors and routing tables.  

---

## ✅ Tasks Completed

### **📝 Task 1: Configure Hostnames & Interfaces for each router**
- Assigned hostnames for R1 to R4.  
- Configured IP addresses on all router interfaces.  
- Enabled interfaces using `no shutdown`.

### **🎯 Task : Configure Loopback Interfaces**
- Added loopback interfaces on each router:  
  - R1 → 1.1.1.1/32  
  - R2 → 2.2.2.2/32  
  - R3 → 3.3.3.3/32  
  - R4 → 4.4.4.4/32

### **🔁 Task 3: Configure EIGRP**
- Enabled EIGRP AS 100 on all routers.  
- Disabled auto-summary.  
- Enabled passive interfaces (loopbacks included).  
- Verified routes and neighbors using:  
  - `show ip protocols`  
  - `show ip eigrp neighbors`  
  - `show ip route eigrp`

  
