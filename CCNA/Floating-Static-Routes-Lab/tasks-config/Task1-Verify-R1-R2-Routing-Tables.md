# 🧪 Task 1: Verify R1 & R2 Routing Tables

## Topology For Reference:
<img width="653" height="383" alt="topology" src="https://github.com/user-attachments/assets/ecf85e25-687b-419f-aaad-b4d11e150906" />

## 🎯 Goals
1️⃣) Check R1 & R2 routing table and find out which **dynamic routing protocol** Enterprise A is using
2️⃣) Check PC1 to SRV1 route
3️⃣) Check PC1 to Internet SRV(1.1.1.1) route

## 🔍 Step 1: Check R1 Routing Table

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

**Note: The route with the O flag is using OSPF as its dynamic routing protocol**


## 🔍 Step 2: Check R2 Routing Table
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

**Note: The route with the O flag is using OSPF as its dynamic routing protocol**

**Which dynamic routing protocol is Enterprise A using?  Answer: Enterprise A is using OSFP**

## 🖥️ Step 3: Test Connectivity PC1 to SRV1

#### 🔷 Ping SRV1
```bash
ping 10.0.2.1
```

**Exppected Output✅:**

<img width="746" height="368" alt="PC1-SRV1-ping" src="https://github.com/user-attachments/assets/4b215866-8da1-49ee-a4df-8b0b52d7572b" />

**PC1 SRV1 path**

<img width="652" height="404" alt="T1-PC1-SRV1-route" src="https://github.com/user-attachments/assets/19aabf4a-3a79-4dd0-81ee-50705af4a0c3" />

<br/>

#### 🔷 Ping the remote server 1.1.1.1

```bash
ping 10.0.2.1
```

**Exppected Output✅:**

<img width="743" height="369" alt="T1-PC1-RMT-SRV-pinh" src="https://github.com/user-attachments/assets/a5d9903f-d1b7-400d-8ba4-22aaa0bf80b8" />

**PC1 Remote Server path**

<img width="665" height="410" alt="T1-PC1-Int-SRV" src="https://github.com/user-attachments/assets/a464d67f-4d21-4f13-8a7d-3688c9b036d2" />

---

## ✅ Task 1: Quick Summary

- Which dynamic routing protocol is Enterprise A using?
- - Answer: **Enterprise A is using OSF**P
- Which route will be used if PC1 tries to access SRV1?
- - Answer: **It will use the route VIA R2**
- Which route will be used if PC1 tries to access remote server 1.1.1.1 over the Internet?
- - Answer: **The Route Via ISPBR1**


