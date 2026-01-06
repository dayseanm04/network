# 🔀 Task 2 – Configure Router-on-a-Stick (ROAS) for Voice and Data VLANs

## 📌 Objective

Enable **inter-VLAN routing** for:
- 🖥️ **Data VLAN 10** (PCs)
- 📞 **Voice VLAN 20** (IP Phones)

This is done using **Router-on-a-Stick (ROAS)**:

- The **SW1 ↔ R1** link is a **trunk**
- R1 uses **subinterfaces** (one per VLAN) with **802.1Q encapsulation**

---

## 📋 VLAN & Gateway Plan

| VLAN Type | VLAN ID | Subnet | Default Gateway (R1) |
|----------|--------|--------|-----------------------|
| 🖥️ Data | 10 | 192.168.10.0/24 | 192.168.10.1 |
| 📞 Voice | 20 | 192.168.20.0/24 | 192.168.20.1 |

---

## Topology For Reference

<img width="657" height="253" alt="topology" src="https://github.com/user-attachments/assets/3459f83e-c98d-4bca-826a-c8d8641898e7" />

---

## ⚙️ Part A — Configure the Trunk on SW1 (G1/0/1)

### 1️⃣ Enter Global Config Mode

```bash
configure terminal
```

### 2️⃣ Select the Uplink Interface to R1

```bash
interface g1/0/1
```

### 3️⃣ Set the Interface as a Trunk

```bash
switchport mode trunk
```

### 4️⃣ Allow Only the Needed VLANs (10 and 20)

```bash
switchport trunk allowed vlan 10,20
```
### 5️⃣ Exit

```bash
end
```

## ✅ Verify Trunking on SW1

```bash
show interfaces trunk
```

<img width="791" height="240" alt="T2-show-interface-trunk" src="https://github.com/user-attachments/assets/f2f66c93-3bc6-445c-8b43-f78f6d570bfa" />


## ⚙️ Part B — Configure ROAS on R1 (F0/0 Subinterfaces)

### 1️⃣ Enter Global Config Mode

```bash
enable
conf t
```

### 2️⃣ Enable the Physical Interface

```bash
interface f0/0
no shutdown
exit
```

### 3️⃣ Create Subinterface for Data VLAN 10

```bash
interface f0/0.10
encapsulation dot1q 10
ip address 192.168.10.1 255.255.255.0
exit
```











