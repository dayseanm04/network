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

#### 🔷 View the routing table

```bash
do show ip route
```

**Expected Output ✅:**

<img width="808" height="392" alt="T3-R1-show-IP-route" src="https://github.com/user-attachments/assets/442f8a9d-d702-4c60-a89c-c4be52071af2" />




