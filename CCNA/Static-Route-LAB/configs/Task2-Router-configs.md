# Task2 Configuring static routes on the routers

### Objective: Configure static routes on the routers

## Topology For Reference
<img width="695" height="280" alt="Topology" src="https://github.com/user-attachments/assets/aae3b0a8-1b51-4f82-8adc-49591e9dd093" />

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
<img width="809" height="338" alt="R1 RT" src="https://github.com/user-attachments/assets/a05e58f2-674a-4c77-8874-eb1e1e4e15b6" />


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
<img width="809" height="361" alt="R2-RT" src="https://github.com/user-attachments/assets/8be2c06c-4ea0-469f-a5d2-493b72e11425" />

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
<img width="729" height="374" alt="R3-RT" src="https://github.com/user-attachments/assets/dda9deaf-9f81-45c9-9b86-f32a728643fa" />
