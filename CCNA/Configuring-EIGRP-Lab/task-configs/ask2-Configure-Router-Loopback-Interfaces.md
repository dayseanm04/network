# 🧩 Task 2: Configure Router Loopback Interfaces

## Topology For reference

<img width="599" height="320" alt="topology" src="https://github.com/user-attachments/assets/e146f7b8-7977-42ce-8984-0c92d4d92d0d" />

## 🎯 Goal

In this task I will configure a **loopback interface** on each router.  
Each router gets a unique /32 IP address:

- R1 → `1.1.1.1/32`
- R2 → `2.2.2.2/32`
- R3 → `3.3.3.3/32`
- R4 → `4.4.4.4/32`

These loopbacks will later be advertised in EIGRP and used for testing reachability.

## 🖥️ R1: Configure Loopback Interface

<br/>

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Configure R1 Loopback0
```bash
interface loopback0
```

**Expected Output ✅:**

<img width="830" height="134" alt="T2-R1-loopback-log-msg" src="https://github.com/user-attachments/assets/89017537-8c5e-40ef-a5b7-c3a5e1f98434" />

### 3️⃣ Configure R1 Loopback0 IP

```bash
ip address 1.1.1.1 255.255.255.255
end
```

### 4️⃣ Verify

```bash
show ip in brief
```

<img width="845" height="122" alt="T2-R1-show-ip-int" src="https://github.com/user-attachments/assets/4503aeea-2d94-4ce6-89f1-c50c7c9ff152" />

### 5️⃣ Save

```bash
write memory
```

## 🖥️ R2: Configure Loopback Interface

<br/>

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Configure R2 Loopback0 and assign the IP

```bash
interface loopback0
ip address 2.2.2.2 255.255.255.255
end
```

### 3️⃣ Verify

```bash
show ip int brief
```

**Expected Output ✅:**

<img width="818" height="118" alt="T2-R2-show-ip-int" src="https://github.com/user-attachments/assets/9dec7ab7-bde8-4712-b23f-1c88b2ad9e78" />


### 4️⃣ Save

```bash
show ip int brief
```

## 🖥️ R3: Configure Loopback Interface

<br/>

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Configure R2 Loopback0 and assign the IP

```bash
interface loopback0
ip address 3.3.3.3 255.255.255.255
end
```

### 3️⃣ Verify

```bash
show ip int brief
```

**Expected Output ✅:**

<img width="810" height="116" alt="T2-R3-show-ip-int" src="https://github.com/user-attachments/assets/a8a77e96-3a89-4987-bb1a-3ffe6f3815d1" />


### 4️⃣ Save

```bash
show ip int brief
```

