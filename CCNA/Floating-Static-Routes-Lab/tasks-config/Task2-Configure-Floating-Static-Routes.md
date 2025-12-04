# 🚦 Task 2: Configure Floating Static Routes

## 🎯 Goal
In this task I will configure **floating static routes** on **R1** and **R2** so that PC1 can still reach SRV1 if the direct link between R1 and R2 goes down.

<br/>

A floating static route is just a normal static route with a **higher administrative distance (AD)** than the dynamic protocol (OSPF).  
- OSPF AD = 110  
- Floating static route AD = 115 (backup route)

## 🖧 1️⃣ Configure Floating Static Route on R1

#### 🔷 Enter global configuration mode:

```bash
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

**Expected Output✅:**
<img width="808" height="447" alt="T2-show-route-R1" src="https://github.com/user-attachments/assets/86c02fae-d5e2-48c2-b0bb-777f14b998e2" />

**View Diagram below:**

<img width="697" height="418" alt="if-R1-R2-link-is-down" src="https://github.com/user-attachments/assets/008b2fa3-88ef-4612-8115-a77db366c0a1" />


## 🖧 2️⃣ Configure Floating Static Route on R1

#### 🔷 Enter global configuration mode:

```bash
enable
configure terminal
```

#### 🔷 Configure floating static route on R1 (to the SRV1 network)
```bash
ip route 10.0.1.0 255.255.255.0 203.0.113.5 115
```

##### ♦️ Check the R2 routing table
```bash
do show ip route
```

**Expected Output✅:**

<img width="802" height="450" alt="T2-show-route-R2" src="https://github.com/user-attachments/assets/f4396922-ad1a-4664-a545-0f557bade8d3" />

**View Diagram below:**

<img width="697" height="418" alt="if-R2-R1-link-is-down" src="https://github.com/user-attachments/assets/d02b639a-e21e-4b4a-b6e3-908147f685f9" />
