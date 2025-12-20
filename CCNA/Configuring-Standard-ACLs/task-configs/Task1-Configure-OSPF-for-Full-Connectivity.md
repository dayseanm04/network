# Task1 Configure OSPF for Full Connectivity.md 🌐🧭

## 🎯 Goal
Configure **OSPF** on **R1** and **R2** so that **all PCs and servers can fully communicate** before applying any ACLs.  

## Topology For Reference

<img width="734" height="267" alt="topology" src="https://github.com/user-attachments/assets/57bf3181-0365-471e-a3e5-86c4aab1af4e" />


## 🛠️ Configure OSPF on R1

### 1️⃣ Enter privileged EXEC mode

```bash
enable
```

### 2️⃣ Enter global configuration mode

```bash
configure terminal
```

### 3️⃣ Enter OSPF configuration mode

```bash
router ospf 1
```

### 4️⃣ Enable OSPF on appropraite interfaces

```bash
network 203.0.113.0 0.0.0.3 area 0
network 172.16.1.0 0.0.0.255 area 0
network 172.16.2.0 0.0.0.255 area 0
```

### 5️⃣ Exit configuration mode

```bash
do show ip protocols
```

**Expected Output✅:**

<img width="733" height="372" alt="T1-R1-verify-ospf" src="https://github.com/user-attachments/assets/994f2384-de73-443b-9ac8-9d22a15a6d21" />


## 🛠️ Configure OSPF on R2

### 1️⃣ Enter privileged EXEC mode

```bash
enable
```

### 2️⃣ Enter global configuration mode

```bash
configure terminal
```

### 3️⃣ Enter OSPF configuration mode

```bash
router ospf 1
```

### 4️⃣ Enable OSPF on appropraite interfaces

```bash
network 203.0.113.0 0.0.0.3 area 0
network 192.168.1.0 0.0.0.255 area 0
network 192.168.2.0 0.0.0.255 area 0
```

<img width="683" height="45" alt="T1-R2-forms-adj" src="https://github.com/user-attachments/assets/c31d68f3-71e4-4012-ba42-0b04e7225967" />

**Note:** R2 becomes neighbors with R1




