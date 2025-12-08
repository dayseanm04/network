# 🌐 Task 4 – Configure R1 as an ASBR

## 🎯 Goal

In this task, I will configure **R1** as an **ASBR (Autonomous System Border Router)**.  
R1 will:
- Have a **default static route** pointing to the ISP.
- **Advertise** that default route into the **OSPF domain** so that R2, R3, and R4 can use it as their path to the Internet.

## Topology For Reference

<img width="711" height="341" alt="Topology" src="https://github.com/user-attachments/assets/53e6080d-57be-4f5f-b410-c3046016c538" />

## 🔍 1️⃣ Check R1 routing table

### 1️⃣ Enter privileged EXEC mode

```bash
enable
```

### 2️⃣ View R1 routing table

```bash
show ip route
```

**Expected Ouput ✅:**

<img width="876" height="538" alt="T5-R1-show-route" src="https://github.com/user-attachments/assets/5f27aba4-d790-4876-910d-3de919ab36b5" />

**Note: theres no defaault Route on R1**

## 🛣️ 2️⃣ Configure a Default Static Route on R1

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Configure the default static route

```bash
ip route 0.0.0.0 0.0.0.0 203.0.113.2
```

### 3️⃣ Check the default route on R1

```bash
do show ip route
```

**Expected Ouput ✅:**

<img width="892" height="564" alt="T5-R1-show-route-after" src="https://github.com/user-attachments/assets/3e5c5386-1671-4e9b-bd7d-d01a847b2d6b" />

## 📢 3️⃣ Advertise the Default Route into OSPF

### 1️⃣ Enter global configuration mode again (skip if in global mode)

```bash
enable
configure terminal
```

### 2️⃣ Enter OSPF process configuration

```bash
router ospf 1
```

### 3️⃣ Advertise the default route

```bash
default-information originate
```

### 4️⃣ Verify

```bash
do show ip protocols
```

**Expected Ouput ✅:**

<img width="718" height="428" alt="T5-R1-show-ip-protocols" src="https://github.com/user-attachments/assets/25c6511a-8bba-4b88-b06c-6344d7facf97" />




