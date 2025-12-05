# 🧩 Task 1: Configure Hostnames and IP Addresses

## Topology For reference

<img width="599" height="320" alt="topology" src="https://github.com/user-attachments/assets/e146f7b8-7977-42ce-8984-0c92d4d92d0d" />

In this task I will:

- Configure the **hostname** on each router (R1–R4).
- Configure the **IP address** on each interface.
- Use `no shutdown` command to **enable all router interfaces**.

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
```

### 5️⃣ Exit back to privileged EXEC mode (optional)

```bash
end
write memory
```

