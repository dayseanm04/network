# Task2 Configuring static routes on the routers

### Objective: Configure static routes on the routers

## Topology For Reference

<img width="787" height="320" alt="topology" src="https://github.com/user-attachments/assets/3d2ff2ca-f7af-4da0-a089-917e6760307b" />

---
## 🧭 Static Route Table

| **Router** | **Destination Network** | **Next Hop** |
|-------------|--------------------------|---------------|
| **R1** | 192.168.1.0/24 | Connected |
| **R1** | 192.168.3.0/24 | 192.168.12.2 |
| **R2** | 192.168.1.0/24 | 192.168.12.1 |
| **R2** | 192.168.3.0/24 | 192.168.13.3 |
| **R3** | 192.168.1.0/24 | 192.168.13.2 |
| **R3** | 192.168.3.0/24 | Connected |

---

## R1 Static Route Configuration
**Goal:** Configure static route on R1 so it can reach the 192.168.3.0/24 network (PC2).

### 🔓 Step 1: Enter Global Configuration Mode
**Commands:**
```bash
en
conf t
```
**Note: en is the shortcut of enable and conf t is the shortcut for configure terninal**


### 🌐 Step 2: Configure static route to PC2's network(192.168.3.0/24) via R2
**Commands:**
```bash
ip route 192.168.3.0 255.255.255.0 192.168.12.2
```

### 🌐 Step 3: Verfiy
```bash
show ip route
```

**Expected Output ✅**

<img width="813" height="341" alt="R1 RT" src="https://github.com/user-attachments/assets/c85d2fd5-0849-44ab-98a7-882f997d25cc" />


---

## R2 Static Route Configuration
**Goal:** Configure static route on R2 so it can reach the 192.168.3.0/24 and 192.168.1.0/24 networks.

### 🔓 Step 1: Enter Global Configuration Mode
**Commands:**
```bash
en
conf t
```

### 🌐 Step 2: Configure static route to PC2's network via R2
**Commands:**
```bash
ip route 192.168.3.0 255.255.255.0 192.168.13.3
```

### 🌐 Step 2: Configure static route to PC2's network (192.168.3.0/24) and PC1 network(192.168.1.0/24)
**Commands:**
```bash
ip route 192.168.1.0 255.255.255.0 192.168.12.1
```

### 🌐 Step 3: Verfiy
```bash
show ip route
```
**Expected Output ✅**

<img width="814" height="365" alt="R2-RT" src="https://github.com/user-attachments/assets/6da5d123-d5c8-4652-bd8c-c747a92e89a5" />

---

## R3 Static Route Configuration
**Goal:** Configure static route on R3 so it can reach PC1's 192.168.3.0/24 network.

### 🔓 Step 1: Enter Global Configuration Mode
**Commands:**
```bash
en
conf t
```

### 🌐 Step 2: Configure static route to PC1's network via R2
**Commands:**
```bash
ip route 192.168.3.0 255.255.255.0 192.168.13.2
```

### 🌐 Step 3: Verfiy
```bash
show ip route
```
**Expected Output ✅**

<img width="733" height="377" alt="R3-RT" src="https://github.com/user-attachments/assets/c799ced3-0b74-48b0-bdad-b5371870221b" />
