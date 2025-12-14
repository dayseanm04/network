# Task3 Fix OSPF Neighbor Issue With R5.md 🔄🤝

## 🎯 Goal
R2 and R4 will not become OSPF neighbors with **R5**.  
Troubleshoot why the adjacency is failing and fix the issue so R5 forms neighbors successfully.

## Topology For Reference

<img width="707" height="307" alt="topololgy" src="https://github.com/user-attachments/assets/5f516c89-9322-44b4-8128-ff659905e275" />

---

## 🧪 Step-by-Step: Confirm the Neighbor Problem

### 1️⃣ On R2: Check OSPF neighbors

```bash
enable
show ip ospf neighbor
```

**Expected Output ✅:**

<img width="864" height="119" alt="T3-R2-show-ospf-neighbor" src="https://github.com/user-attachments/assets/aed325e7-4fdc-4a67-82f0-871ae782fa14" />

**Note:** R2 and R4 are neighbors

### 2️⃣ On R4: Check OSPF neighbors

```bash
enable
show ip ospf neighbor
```

**Expected Output ✅:**

<img width="879" height="122" alt="T3-R4-show-ospf-neighbor" src="https://github.com/user-attachments/assets/d1ce5c8c-16d6-46d6-887e-43b273a15ae9" />

**Note:** R4 and R2 are neighbors

### 3️⃣ On R5: Check OSPF neighbors

```bash
enable
show ip ospf neighbor
```

**Expected Output ✅:**

<img width="636" height="59" alt="T3-R5-show-ospf-neighbor" src="https://github.com/user-attachments/assets/f0eee28a-ab52-435c-962c-fd111bce19ff" />

**Note:** R5 dosent have any neighbors

## 🔎 Step-by-Step: Check the Shared Network Interface

### 4️⃣ On R2: Check OSPF settings on G0/0

```bash
show ip ospf interface g0/0
```

**Expected Output ✅:**

<img width="797" height="313" alt="T3-R2-show-g00-int" src="https://github.com/user-attachments/assets/badaaded-b6fc-44b2-83b4-9bb5eccabfa1" />

**Note:** R2 G0/0 interface hello timer is 10 and its dead timer is 40

### 5️⃣ On R4: Check OSPF settings on G0/0

```bash
show ip ospf interface g0/0
```

**Expected Output ✅:**

<img width="811" height="315" alt="T3-R4-show-g00-int" src="https://github.com/user-attachments/assets/bd01197d-3ba8-4458-89ac-ccbf26288719" />

**Note:** R4 G0/0 interface hello timer is 10 and its dead timer is 40
