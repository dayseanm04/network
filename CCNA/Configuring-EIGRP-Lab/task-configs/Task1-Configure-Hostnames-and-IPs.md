# 🧩 Task 1: Configure Hostnames and IP Addresses

## Topology For reference

<img width="599" height="320" alt="topology" src="https://github.com/user-attachments/assets/e146f7b8-7977-42ce-8984-0c92d4d92d0d" />

In this task I will:

- Configure the **hostname** on each router (R1–R4).
- Configure the **IP address** on each interface.
- Use `no shutdown` command to **enable all router interfaces**.

## 🖥️ R1: Hostname and Interfaces

<br/>

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Configure R1 hostname

```bash
hostname R1
```

### 3️⃣ Configure FastEthernet1/0 (to R3)

```bash
interface f1/0
ip address 10.0.13.1 255.255.255.252
no shutdown
```

### 4️⃣ Configure GigabitEthernet0/0 (to R2)

```bash
interface g0/0
ip address 10.0.12.1 255.255.255.252
no shutdown
end
```

### 5️⃣ Verify

```bash
show ip int brief
```

**Expected Output ✅:**

<img width="821" height="100" alt="T1-R1-show-ip-int" src="https://github.com/user-attachments/assets/2901c679-94c1-4d6d-8e15-44becd780180" />


### 6️⃣ Save

```bash
write memory
```

## 🖥️ R2: Hostname and Interfaces

<br/>

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Configure R2 hostname

```bash
hostname R2
```

### 3️⃣ Configure FastEthernet1/0 (to R4)

```bash
interface f1/0
ip address 10.0.24.1 255.255.255.252
no shutdown
```

### 4️⃣ Configure GigabitEthernet0/0 (to R1)

```bash
interface g0/0
ip address 10.0.12.2 255.255.255.252
no shutdown
end
```

### 5️⃣ Verify

```bash
show ip int brief
```

**Expected Output ✅:**

<img width="813" height="99" alt="T1-R2-show-ip-int" src="https://github.com/user-attachments/assets/ee34abf5-5bd7-42c8-9788-49137e072e17" />


### 6️⃣ Save

```bash
write memory
```

## 🖥️ R3: Hostname and Interfaces

<br/>

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Configure R3 hostname

```bash
hostname R3
```

### 3️⃣ Configure FastEthernet1/0 (to R1)

```bash
interface f1/0
ip address 10.0.13.2 255.255.255.252
no shutdown
```

### 4️⃣ Configure FastEthernet2/0 (to R4)

```bash
interface f2/0
ip address 10.0.34.1 255.255.255.252
no shutdown
end
```

### 5️⃣ Verify

```bash
show ip int brief
```

**Expected Output ✅:**

<img width="812" height="98" alt="T1-R3-show-ip-int" src="https://github.com/user-attachments/assets/670b9a04-731d-43f6-a809-10379b117d0b" />


### 6️⃣ Save

```bash
write memory
```

## 🖥️ R4: Hostname and Interfaces

<br/>

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Configure R4 hostname

```bash
hostname R4
```

### 3️⃣ Configure FastEthernet2/0 (to R3)

```bash
interface f2/0
ip address 10.0.34.2 255.255.255.252
no shutdown
```

### 4️⃣ Configure FastEthernet1/0 (to R2)

```bash
interface f1/0
ip address 10.0.24.2 255.255.255.252
no shutdown
```

### 5️⃣ Configure GigabitEthernet0/0 (to LAN 192.168.4.0/24)

```bash
interface g0/0
ip address 192.168.4.254 255.255.255.0
no shutdown
end
```

### 6️⃣ Verify

```bash
show ip int brief
```

**Expected Output ✅:**

<img width="833" height="102" alt="T1-R4-show-ip-int" src="https://github.com/user-attachments/assets/93a0b708-7350-4b82-9e15-3d6f048e5ffb" />

### 7️⃣ Save

```bash
write memory
```

