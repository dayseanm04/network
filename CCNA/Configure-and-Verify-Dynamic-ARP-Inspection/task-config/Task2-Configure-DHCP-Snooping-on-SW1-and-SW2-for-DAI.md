# 🔐 Configure DHCP Snooping for DAI

## 📌 Objective

Enable **DHCP Snooping** on **SW1** and **SW2** to build a **trusted IP-to-MAC binding table**.  
These bindings are required for **Dynamic ARP Inspection (DAI)** to validate ARP packets.

---

## 🧠 Simple Explanation

- DHCP Snooping inspects DHCP traffic
- Only **trusted interfaces** are allowed to forward DHCP server messages
- Client-facing ports stay **untrusted by default**
- The switch records **IP–MAC bindings**, which DAI will use later

📌 Think of DHCP Snooping as the **foundation** for DAI.

## Topology For Reference

<img width="685" height="260" alt="topology" src="https://github.com/user-attachments/assets/6b428763-7bbc-4f14-aefa-c2624a090abc" />

---

## 📋 What I Will Configure

- Enable DHCP Snooping globally
- Enable DHCP Snooping for **VLAN 1**
- Disable the DHCP information option (Option 82)
- Trust **uplink interfaces** connected to a router or another switch

---

## ⚙️ Configure – SW1

### 1️⃣ Enter Global Configuration Mode
```bash
enable
configure terminal
```

### 2️⃣ Enable DHCP Snooping

```bash
ip dhcp snooping
```

### 3️⃣ Enable DHCP Snooping for VLAN 1

```bash
ip dhcp snooping vlan 1
```

### 4️⃣ Disable DHCP Snooping Information Option (Option 82)

```bash
no ip dhcp snooping information option
```

### 5️⃣ Trust the Uplink Interface (Connected to Router/Switch)

```bash
interface g0/2
ip dhcp snooping trust
```

### 6️⃣ Exit

```bash
end
```

## ⚙️ Configure – SW2

### 1️⃣ Enter Global Configuration Mode

```bash
enable
configure terminal
```

### 3️⃣ Enable DHCP Snooping for VLAN 1

```bash
ip dhcp snooping vlan 1
```

### 4️⃣ Disable DHCP Snooping Information Option (Option 82)

```bash
no ip dhcp snooping information option
```

### 5️⃣ Trust the Uplink Interface (Connected to Router/Switch)

```bash
interface g0/1
ip dhcp snooping trust
```











