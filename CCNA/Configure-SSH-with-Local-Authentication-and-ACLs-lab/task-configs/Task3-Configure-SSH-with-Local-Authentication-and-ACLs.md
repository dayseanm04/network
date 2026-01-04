# 🔐 Task 3 - Configure SSH with Local Authentication and ACLs (SW2)

## 🎯 Goal
Configure **SW2** for secure remote management using **SSH only** with:

- ✅ **Local user authentication**
- ✅ **RSA keys (2048-bit)**
- ✅ **Exec timeout (5 minutes)**
- ✅ **SSH-only access (no Telnet)**
- ✅ **ACL restriction: allow ONLY PC1 to SSH into SW2**


## Reference Topology

<img width="545" height="224" alt="topology" src="https://github.com/user-attachments/assets/ae47e659-6807-4ae7-9c97-e89aa8e4ebba" />

---


## 🧩 Step-by-Step Config

### 1️⃣ Enter Global config Mode

On **Laptop**:

```bash
enable
configure terminal
```

**Note 📢: laptop is consoled into SW2**

## 🌐 Part A - Enable SSH (Domain + RSA Keys)

### 2️⃣ Configure the Domain Name

```bash
ip domain-name jeremysitlab.com
```

### 3️⃣ Generate RSA Keys (2048-bit)

```bash
crypto key generate rsa
```

**When prompted, enter: 2048**

## 🧱 Part B 🧱 Part B - Create ACL to Allow ONLY PC1 Create ACL to Allow ONLY PC1

### 4️⃣ Create a Standard ACL Permitting PC1 Only\

```bash
access-list 1 permit host 192.168.1.1
```

## 🧰 Part C - Configure VTY Lines for SSH + Local Login + ACL

### 5️⃣ Configure VTY Lines (0–15)

```bash
line vty 0 15
```

### 6️⃣ Enable Local Authentication + Timeout

```bash
login local
exec-timeout 5
```

### 7️⃣ Allow SSH Only (Disable Telnet)

```bash
transport input ssh
```

### 8️⃣ Apply ACL to Limit SSH to PC1 Only

```bash
access-class 1 in
```
