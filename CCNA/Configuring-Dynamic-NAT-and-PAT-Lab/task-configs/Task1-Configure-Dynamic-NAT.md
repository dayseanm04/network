# 🌐 Task 1 – Configure Dynamic NAT on R1

## 🎯 Goal
Configure **Dynamic NAT** on **R1** so that hosts in `172.16.0.0/24` can access the internet using a **public IP pool** from `100.0.0.1` to `100.0.0.2` (subnet `100.0.0.0/24`).

## Topology For Reference

<img width="588" height="215" alt="Topology" src="https://github.com/user-attachments/assets/a0ad75ab-6982-416a-8c01-5fd83306f1b0" />

---

## ✅Configure R1

### 1️⃣ Enter Global Configuration Mode

```bash
enable
configure terminal
```


### 2️⃣ Configure the NAT Outside Interface (Internet Side)

```bash
interface g0/0
ip nat outside
```

**📌Note:  This tells R1 that traffic leaving this interface is going to the internet.**

### 3️⃣ Configure the NAT Inside Interface (LAN Side)

```bash
interface g0/1
ip nat inside
```

**✅ Now R1 knows which side is inside and which side is outside.**


### 4️⃣ Create an standard  ACL to Match Inside Traffic (172.16.0.0/24)

```bash
access-list 1 permit 172.16.0.0 0.0.0.255
```

**📌Note: This ACL defines which inside hosts are allowed to be translated.**

### 5️⃣ Create the Public NAT Pool

```bash
ip nat pool public 100.0.0.1 100.0.0.2 netmask 255.255.255.0
```

### 6️⃣ Enable Dynamic NAT

```bash
ip nat inside source list 1 pool public
```

**📌Note: This tells R1 to translate traffic matched by ACL 1 using the pool**

### 7️⃣ Verify NAT is Configured

```bash
do show ip nat statistics
```

<img width="706" height="231" alt="T1-nat-stat" src="https://github.com/user-attachments/assets/8741b680-ecdc-457e-93d4-1747dfccec03" />




















