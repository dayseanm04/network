# Task2 Troubleshoot OSPF Missing-Route 🔍🧭

## 🎯 Goal
Only **R3** has a route to **10.0.2.0/24**.  
Find out **why other routers don’t learn it through OSPF**, then fix the issue so the route propagates across the OSPF domain.

## Topology For Reference

<img width="707" height="307" alt="topololgy" src="https://github.com/user-attachments/assets/5f516c89-9322-44b4-8128-ff659905e275" />


---

## 🧪 Step-by-Step: Confirm the Problem

### 1️⃣ Check R3's routing table

```bash
enable
show ip route
```

**Expected Output ✅:**

<img width="832" height="324" alt="T2-R3-route" src="https://github.com/user-attachments/assets/57deb459-c951-4f10-817a-109b550ae482" />

**Note:** R3 has the route to 10.0.2.0/24 network because its directly connected on its G0/0 interface

## 2️⃣ Check R4's routing table

```bash
enable
show ip route
```

**Expected Output ✅:**

<img width="832" height="362" alt="T2-R4-show-ip-route1" src="https://github.com/user-attachments/assets/99653abb-a16e-42bd-b85a-b024611eb9dc" />

---

## 🔎 Step-by-Step: Check OSPF on the Link (R3 ↔ R4)

### 1️⃣ On R3: Check the interface connected to R4

**Note:** In this lab, R3 connects to R4 using G0/1 interface.

### 2️⃣ Check OSPF settings on R3 G0/1 interface

```bash
show ip ospf interface g0/1
```

**Expected Output ✅:**

<img width="782" height="280" alt="T2-R3-g01-int" src="https://github.com/user-attachments/assets/e67df5c0-edb3-4622-8061-9f43adc8da9b" />

**Note:** R3 G0/1 interface network type is Point-To-Point

### 3️⃣ On R4: Check OSPF settings on the matching interface

**Note:** In this lab, R4 connects to R3 using G0/1 interface.

```bash
show ip ospf interface g0/1
```

**Expected Output ✅:**

<img width="773" height="315" alt="T2-R4-g01-int" src="https://github.com/user-attachments/assets/49e2eece-fde9-4c84-9902-268203968054" />

**Note:** R4 G0/1 interface network type is Broadcast.

###  The OSPF network type must match on both ends.

---

## 🛠️ Fix: Correct the OSPF Network Type Mismatch

### 1️⃣ On R3: Enter interface configuration

```bash
configure terminal
interface g0/1
```

### 2️⃣ Remove the point-to-point OSPF network type (restore default)

```bash
no ip ospf network point-to-point
```

**Expected Output ✅:**

<img width="969" height="113" alt="T2-remove-r3-p2p" src="https://github.com/user-attachments/assets/92ed9c99-6331-4550-a0b2-8962b91c61f5" />

**Note:** R3 G0/1 interface went to the down state and then immediately went to the full state


### ✅ Verify the Fix (Check R4 routing table)

```bash
do show ip route
```

**Expected Output ✅:**

<img width="813" height="366" alt="T2-R4-verify-route" src="https://github.com/user-attachments/assets/0302d516-2ad4-4f74-b970-c28eb30a0c8b" />

**You should now see 10.0.2.0/24 learned via OSPF.**
