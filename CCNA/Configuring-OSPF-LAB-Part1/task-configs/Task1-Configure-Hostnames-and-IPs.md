# 🧩 Task 1 – Configure Hostnames and IP Addresses

## 🎯 Goal

In this task I will:

- Configure the **hostname** on each router (R1–R4).
- Configure the correct **IP address** on each interface.
- Use the `no shutdown` command to **enable the interfaces**.
- I **do not** need to configure **ISPR1** in this task.

Complete this before moving on to loopbacks and OSPF.

## Topology For Reference

<img width="711" height="341" alt="Topology" src="https://github.com/user-attachments/assets/53e6080d-57be-4f5f-b410-c3046016c538" />

---

## 🖥️ R1: Hostname and Interfaces

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Set the hostname

```bash
hostname R1
```

### 3️⃣ Configure GigabitEthernet3/0 (Internet link)

```bash
interface g3/0
ip address 203.0.113.1 255.255.255.252
no shutdown
```

### 4️⃣ Configure FastEthernet1/0 (link to R3)

```bash
interface f1/0
ip address 10.0.13.1 255.255.255.252
no shutdown
```

### 5️⃣ Configure GigabitEthernet0/0 (link to R2)

```bash
interface g0/0
ip address 10.0.12.1 255.255.255.252
no shutdown
```

### 6️⃣ Verify interfaces

```bash
do show ip interface brief
```

**Expected Output ✅:**

<img width="903" height="117" alt="T1-R1-ip-int" src="https://github.com/user-attachments/assets/f5076767-41cb-4279-91b6-4ad53411df08" />

### 7️⃣ Save

```bash
end
write memory
```

---

## 🖥️ R2: Hostname and Interfaces

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Set the hostname

```bash
hostname R2
```

### 3️⃣ Configure FastEthernet1/0 (link to R4)

```bash
interface f1/0
ip address 10.0.24.1 255.255.255.252
no shutdown
```

### 4️⃣ Configure GigabitEthernet0/0 (link to R1)

```bash
interface g0/0
ip address 10.0.12.2 255.255.255.252
no shutdown
```

### 5️⃣ Verify interfaces

```bash
do show ip interface brief
```

**Expected Output ✅:**

<img width="814" height="104" alt="T1-R2-ip-int" src="https://github.com/user-attachments/assets/1dbbf980-a30f-4d87-8be2-801fcf427dd9" />

### 6️⃣ Save

```bash
end
write memory
```

---

## 🖥️ R3: Hostname and Interfaces

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Set the hostname

```bash
hostname R3
```

### 3️⃣ Configure FastEthernet1/0 (link to R1)

```bash
interface f1/0
ip address 10.0.13.2 255.255.255.252
no shutdown
```

### 4️⃣ Configure FastEthernet2/0 (link to R4)

```bash
interface f2/0
ip address 10.0.34.1 255.255.255.252
no shutdown
```

### 5️⃣ Verify interfaces

```bash
do show ip interface brief
```

**Expected Output ✅:**

<img width="839" height="100" alt="T1-R3-ip-int" src="https://github.com/user-attachments/assets/630dc2fd-73bc-45af-b2ec-da176a5c3ef7" />

### 6️⃣ Save

```bash
end
write memory
```

---

## 🖥️ R4: Hostname and Interfaces

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Set the hostname

```bash
hostname R4
```

### 3️⃣ Configure FastEthernet1/0 (link to R2)

```bash
interface f1/0
ip address 10.0.24.2 255.255.255.252
no shutdown
```

### 4️⃣ Configure FastEthernet2/0 (link to R3)

```bash
interface f2/0
ip address 10.0.34.2 255.255.255.252
no shutdown
```

### 5️⃣ Configure GigabitEthernet0/0 (LAN 192.168.4.0/24)

```bash
interface g0/0
ip address 192.168.4.254 255.255.255.0
no shutdown
```

### 6️⃣ Verify interfaces

```bash
do show ip interface brief
```

**Expected Output ✅:**

<img width="793" height="120" alt="T1-R4-ip-int" src="https://github.com/user-attachments/assets/0f3d4d0f-250e-4d8d-9aeb-44a8b6cf2831" />

### 7️⃣ Save

```bash
end
write memory
```
