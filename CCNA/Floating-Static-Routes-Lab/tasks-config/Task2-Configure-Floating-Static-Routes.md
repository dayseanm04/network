# 🚦 Task 2: Configure Floating Static Routes

## 🎯 Goal
In this task I will configure **floating static routes** on **R1** and **R2** so that PC1 can still reach SRV1 if the direct link between R1 and R2 goes down.

<br/>

A floating static route is just a normal static route with a **higher administrative distance (AD)** than the dynamic protocol (OSPF).  
- OSPF AD = 110  
- Floating static route AD = 115 (backup route)

## 🖧 1️⃣ Configure Floating Static Route on R1

#### 🔷 Enter global configuration:

````bash
enable
configure terminal
```

#### 🔷 Configure floating static route on R1 (to the SRV1 network)
```bash
ip route 10.0.2.0 255.255.255.0 203.0.113.1 115
```

##### ♦️ Check the R1 routing table
```bash
do show ip route
```

