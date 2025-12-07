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


