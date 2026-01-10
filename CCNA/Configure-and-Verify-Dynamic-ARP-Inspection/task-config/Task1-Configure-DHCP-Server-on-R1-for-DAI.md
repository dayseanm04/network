# 🛠️ Configure-R1-as-DHCP-Server-for-DAI

## 📌 Objective
Configure **R1** as a **DHCP server** for the LAN.  

This provides the **IP-to-MAC address bindings** that will later be used by **DHCP Snooping** and **Dynamic ARP Inspection (DAI)**.

## 🧠 Simple Explanation

Dynamic ARP Inspection relies on trusted information to decide whether ARP packets are valid.  
That trusted information comes from **DHCP Snooping bindings**, which are built when clients receive IP addresses from a legitimate DHCP server.

📌 This task sets up that **legitimate DHCP server**.

## Topology For Reference

<img width="685" height="260" alt="topology" src="https://github.com/user-attachments/assets/6b428763-7bbc-4f14-aefa-c2624a090abc" />

---

## 🌐 DHCP Network Information

| Item | Value |
|-----|------|
| Network | 192.168.1.0 /24 |
| Default Gateway | 192.168.1.1 |
| Excluded IP Range | 192.168.1.1 – 192.168.1.9 |
| DHCP Server | R1 |

---

## ⚙️ Configuration Steps (R1)

### 1️⃣ Enter Global Configuration Mode

```bash
enable
configure terminal
```

### 2️⃣ Exclude Reserved IP Addresses

```bash
ip dhcp excluded-address 192.168.1.1 192.168.1.9
```

### 3️⃣ Create the DHCP Pool

```bash
ip dhcp pool LAN1
```

### 4️⃣ Configure the Network

```bash
network 192.168.1.0 255.255.255.0
```





