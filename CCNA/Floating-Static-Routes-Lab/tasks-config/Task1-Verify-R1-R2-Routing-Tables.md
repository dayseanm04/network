# 🧪 Task 1: Verify R1 & R2 Routing Tables

## Topology For Reference:
<img width="653" height="383" alt="topology" src="https://github.com/user-attachments/assets/ecf85e25-687b-419f-aaad-b4d11e150906" />

## 🎯 Goals
1️⃣) Check R1 & R2 routing table and find out which **dynamic routing protocol** Enterprise A is using
2️⃣) Check PC1 to SRV1 route
3️⃣) Check PC1 to Internet SRV(1.1.1.1) route

## 🔍 Step 1: Check the R1 Routing Table

#### 🔷 Enter privileged EXEC mode
```bash
enable
```

#### 🔷 View the routing table
```bash
show ip route
```

**Exppected Output✅:**
<img width="838" height="427" alt="T1-R1-show-route" src="https://github.com/user-attachments/assets/1736f820-2add-46ed-b2ba-f03a369d5d8a" />

**Note: The route with the O flag is uings OSPF as its dynamic routing protocol**


## 🔍 Step 2: Check the R1 Routing Table
#### 🔷 Enter privileged EXEC mode
```bash
enable
```

#### 🔷 View the routing table
```bash
show ip route
```

**Exppected Output✅:**
<img width="848" height="417" alt="T1-R2-show-route" src="https://github.com/user-attachments/assets/1b6e19c5-6de1-47e2-85d4-84fe1a054933" />

**Note: The route with the O flag is uings OSPF as its dynamic routing protocol**

**Which dynamic routing protocol is Enterprise A using?  Answer: Enterprise A is using OSFP**

## 🖥️ Step 3: Test Connectivity PC1 to SRV1

#### 🔷 Ping SRV1
```bash
ping 10.0.2.1
```

