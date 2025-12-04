# 🚦 Task 3: Test Floating Static Routes (Failover)

## 🎯 Goal

In this task, I will:
- Shut down the link between **R1** and **R2**
- Watch the **floating static routes** enter the routing tables
- Test that **PC1 can still reach SRV1** using the backup path

## Topology For Reference:
<img width="653" height="383" alt="topology" src="https://github.com/user-attachments/assets/ecf85e25-687b-419f-aaad-b4d11e150906" />

This proves the floating static routes are working as a **backup** when OSPF fails.

---

## 🔌 1️⃣ Shut Down the R1–R2 Link


#### 🔷 Enter Global Config mode on R1:
```bash
enable
configure terminal
```

#### 🔷 Go to interface G0/2/0
```bash
interface G0/2/0
```

#### 🔷 Shut down the interface
```bash
shutdown
```

**Expected Output ✅:**

<img width="971" height="190" alt="T3-R1-int-down" src="https://github.com/user-attachments/assets/9472ace1-4b44-45df-b489-3765948dfb6a" />

#### 🔷 View R1 routing table

```bash
do show ip route
```

**Expected Output ✅:**

<img width="808" height="392" alt="T3-R1-show-IP-route" src="https://github.com/user-attachments/assets/442f8a9d-d702-4c60-a89c-c4be52071af2" />


#### ♦️ Log messsage displayed on R2:

<img width="971" height="139" alt="T3-R2-log-msg" src="https://github.com/user-attachments/assets/a6b729cb-c65f-4deb-b1be-582f43b5af9c" />

#### 🔷 View R2 routing table

```bash
do show ip route
```
<img width="868" height="395" alt="T3-R2-show-ip-route" src="https://github.com/user-attachments/assets/582641cd-9629-4266-b5e7-0503ff5bb0a2" />

## 🖥️ 2️⃣ Test Connectivity from PC1 to SRV1

#### Ping SRV1

```bash
ping 10.0.2.1
```

**Expected Output ✅:**

<img width="746" height="368" alt="PC1-SRV1-ping" src="https://github.com/user-attachments/assets/18873e5d-8c57-4fce-87c0-d5e91e370e5f" />

<br/>
**PC1-SRV1 path**

<img width="683" height="416" alt="T3-PC1-SRV1" src="https://github.com/user-attachments/assets/f301c892-b7cb-4523-a3ee-af47b088fc99" />

**SRV2 traceroute Output ✅:**
<img width="742" height="337" alt="PC1-SRV1-TRACERT" src="https://github.com/user-attachments/assets/911cbe51-2e94-447d-a08f-8a7fe5fc698f" />

<br/>

## 3️⃣ Bring the R1 Link Back Up

#### 🔷 Enter interface configuration mode
```
enable
conf t
int g0/2/0
```

**Expected Output ✅:**

<img width="880" height="207" alt="R1-G020-int-up" src="https://github.com/user-attachments/assets/7b1df5c0-fd3b-4864-a103-e763120c6341" />

**Note: after about a minute this log will be displayed**

#### 🔷 View R1 routing table

```
do show ip route
```

**Expected Output ✅:**
<img width="827" height="420" alt="T3-R1-OSPF-route-back" src="https://github.com/user-attachments/assets/3b274e7a-1ab9-449b-89d3-238a8e3723e3" />

## ✅ Task 3: Quick Summary

- I shut down the R1–R2 link on G0/2/0.
- OSPF routes were removed, and the floating static routes entered the routing tables.
- PC1 could still ping SRV1, proving that the backup static routes work.
- When the link is restored, OSPF becomes the preferred path again and the static routes return to backup status.

**Floating static routes = 🔁 automatic failover when the main path fails.**
