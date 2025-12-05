# 🧩 Task 3:  Configure EIGRP on All Routers

## Topology For reference

<img width="599" height="320" alt="topology" src="https://github.com/user-attachments/assets/e146f7b8-7977-42ce-8984-0c92d4d92d0d" />

## 🎯 Goal


In this task I will:

- Configure **EIGRP AS 100** on **R1, R2, R3, and R4**
- Disable **auto-summary**
- Enable EIGRP on all **interfaces**, including **loopbacks**
- Configure **passive interfaces** where its appropriate (loopbacks and LAN-facing ports)
- Verify EIGRP neighbors and routes


## 🖥️ R4: EIGRP Configuration

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Configure EIGRP on R4 and disable auto-summary

```bash
router eigrp 100
no auto-summary
```

### 3️⃣ Enable EIGRP on R4 interfaces

```bash
network 10.0.24.0 0.0.0.3       ! R4–R2 link
network 10.0.34.0 0.0.0.3       ! R4–R3 link
network 192.168.4.0 0.0.0.255   ! LAN behind R4
network 4.4.4.4 0.0.0.0         ! Loopback0
```

### 4️⃣ Configure passive interfaces on LAN & loopback
```bash
passive-interface g0/0
passive-interface loopback0
```
### 5️⃣ Verify EIGRP on R4

```bash
do show ip protocols
```

**Expected output ✅:**

<img width="837" height="564" alt="T3-R4-EIGRP" src="https://github.com/user-attachments/assets/43e85106-b218-4b7d-938e-1c3019ed5dec" />

</br>

## 🖥️ R3: EIGRP Configuration

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Configure EIGRP on R3 and disable auto-summary

```bash
router eigrp 100
no auto-summary
```

### 3️⃣ Enable EIGRP on R3 interfaces

```bash
network 10.0.13.0 0.0.0.3   ! R3–R1 link
network 10.0.34.0 0.0.0.3   ! R3–R4 link
network 3.3.3.3 0.0.0.0     ! Loopback0
```

### 4️⃣ Configure loopback as a passive interface

```bash
passive-interface loopback0
```

### 5️⃣ Verify EIGRP on R3

```bash
do show ip protocols
```

**Expected output ✅:**

<img width="659" height="456" alt="T3-R3-EIGRP" src="https://github.com/user-attachments/assets/55e4d6d4-f69a-4017-881c-627c1ac9576b" />

<br/>

## 🖥️ R2: EIGRP Configuration

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Configure EIGRP on R2 and disable auto-summary

```bash
router eigrp 100
no auto-summary
```

### 3️⃣ Enable EIGRP on R2 interfaces

```bash
network 10.0.12.0 0.0.0.3   ! R2–R1 link
network 10.0.24.0 0.0.0.3   ! R2–R4 link
network 2.2.2.2 0.0.0.0     ! Loopback0
```

### 4️⃣ Configure loopback as a passive interface

```bash
passive-interface loopback0
```

### 5️⃣ Verify EIGRP on R3

```bash
do show ip protocols
```

**Expected output ✅:**

<img width="674" height="441" alt="T3-R2-EIGRP" src="https://github.com/user-attachments/assets/151afd57-7b3c-4b8b-b6ca-1712a3fc442b" />

<br/>

## 🖥️ R1: EIGRP Configuration

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Configure EIGRP on R1 and disable auto-summary

```bash
router eigrp 100
no auto-summary
```

**Note: 100 is the autonomous System number**

### 3️⃣ Enable EIGRP on R1 interfaces

```bash
network 10.0.12.0 0.0.0.3   ! R1–R2 link
network 10.0.13.0 0.0.0.3   ! R1–R3 link
network 1.1.1.1 0.0.0.0     ! Loopback0
```

**Note: 0.0.0.3 and 0.0.0.0 are wildcard masks**

### 4️⃣ Configure loopback as a passive interface

```bash
passive-interface loopback0
```

### 5️⃣ Verify EIGRP on R1

```bash
do show ip protocols
```

**Expected output ✅:**

<img width="663" height="447" alt="T3-R1-EIGRP" src="https://github.com/user-attachments/assets/3a14d4c5-159b-492e-b55a-928443c1f8cf" />

