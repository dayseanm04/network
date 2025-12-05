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

### 2️⃣ Configure R1 Loopback0 and assign the IP
```bash
interface loopback0
ip address 1.1.1.1 255.255.255.255
```

### 3️⃣ Exit / save (optional)
```bash
end
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
```

### 3️⃣ Exit / save (optional)
```bash
end
write memory
```

