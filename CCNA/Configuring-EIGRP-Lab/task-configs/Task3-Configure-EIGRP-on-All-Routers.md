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

### 3️⃣ Advertise R1 networks

```bash
network 10.0.12.0 0.0.0.3   ! R1–R2 link
network 10.0.13.0 0.0.0.3   ! R1–R3 link
network 1.1.1.1 0.0.0.0     ! Loopback0
```
