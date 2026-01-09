# 🔐 Task 2 – Configure-DHCP-Snooping-and-Trusted-Interfaces

## 📌 Objective

Enable **DHCP Snooping** on **SW1** and **SW2** to protect the network from **rogue DHCP servers**.

I will also configurr the **uplink interfaces** as **trusted** so DHCP server replies can sent by the switches.

## 🧠 Simple Explanation

DHCP Snooping works by:
- ✅ Allowing DHCP server messages only on **trusted ports**
- 🚫 Blocking DHCP server messages coming from **untrusted ports**

📌 End-user access ports stay **untrusted** by default, which is what we want.

## Topology For Reference

<img width="667" height="221" alt="topology" src="https://github.com/user-attachments/assets/0437e21d-9c1c-483d-b25a-dc0aa1e8f15a" />

---

## 📋 What I Will Configure

### ✅ Enable DHCP Snooping on:
- SW1
- SW2

### ✅ Enable DHCP Snooping for:
- VLAN 1

### ✅ Trust the uplinks:
- SW1 **G0/2** (uplink toward DHCP server side)
- SW2 **G0/1** (uplink toward SW1)

---

## ⚙️ Configuration – SW1

### 1️⃣ Enter Global Config Mode

```bash
enable
configure terminal
```

### 2️⃣ Enable DHCP Snooping

```bash
ip dhcp snooping
```

### 3️⃣ Enable DHCP Snooping on VLAN 1

```bash
ip dhcp snooping vlan 1
```

### 4️⃣ Trust the Uplink Interface (G0/2)

```bash
interface g0/2
ip dhcp snooping trust
```

### 5️⃣ Exit

```bash
end
```

### ✅ Verfiy SW1 DHCP snooping

#### 🔷 On SW1 show ip dhcp snooping

<img width="711" height="276" alt="T2-SW2-show-dhcp-b" src="https://github.com/user-attachments/assets/dfc252e9-704f-446a-bff0-6e014fcfb548" />








