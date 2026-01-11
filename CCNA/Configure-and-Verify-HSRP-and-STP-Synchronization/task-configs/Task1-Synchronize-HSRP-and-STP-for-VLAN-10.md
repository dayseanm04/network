# 🔁 Task1 Synchronize HSRP and STP for VLAN 10

## 📌 Objective

Synchronize **HSRP** and **STP** roles for **VLAN 10** so that:
- **DSW1** is the **HSRP Active Gateway** and **STP Root Bridge**
- **DSW2** is the **HSRP Standby Gateway** and **STP Secondary Root**

This alignment ensures hosts in VLAN 10 use the **most direct path** to their default gateway.

---

## 🧠 Simple Explanation
- **STP** controls the Layer 2 path to the root bridge
- **HSRP** controls the Layer 3 default gateway
- When the **HSRP Active = STP Root**, traffic flows efficiently

## Topology For Reference

<img width="618" height="332" alt="Topology" src="https://github.com/user-attachments/assets/67061080-b132-4e96-a33b-6c05489f583e" />

## 📋 VLAN 10 Role Assignment

| Device | HSRP Role | STP Role |
|-------|-----------|----------|
| DSW1 | 🟢 Active | 🟢 Root |
| DSW2 | 🔵 Standby | 🔵 Secondary Root |

## 📋 VLAN 10 HSRP configs

| Setting | Value |
|------|------|
| HSRP Version | 2 |
| HSRP Group | 10 |
| Virtual IP (VIP) | 10.0.10.200 |
| DSW1 Priority | 120 |
| DSW2 Priority | 80 |
| Preempt | Enabled |

---

# 🟢 Part A - Configure DSW1 (HSRP Active + STP Root)

## 1️⃣ Make DSW1 the STP Root for VLAN 10

#### ♦️ On **DSW1** (Global Config Mode):

```bash
spanning-tree vlan 10 root primary
```

## 2️⃣ Enable HSRP Version 2 on VLAN 10 SVI

```bash
interface vlan 10
standby version 2
```

### 3️⃣ Configure HSRP virtual IP for VLAN 10

```bash
standby 10 ip 10.0.10.200
```

Note: The Virtual IP (VIP) is the default gateway used by hosts in VLAN 10

### 4️⃣ Make DSW1 the Active router

```bash
standby 10 priority 120
```

Note: by defaulut the priority is 100, 120 is higher than 100 so it becomes the active router 

### 5️⃣ Configure Preemption

```bash
standby 10 preempt
```

Note: preempt allows DSW1 to take back the Active role if it comes back online after a failure

## ✅ Verify on DSW1

#### ♦️ show spanning-tree vlan 10

<img width="806" height="358" alt="T1-DSW1-show-stp-vlan10" src="https://github.com/user-attachments/assets/2e5f8bc2-0798-4341-a748-1684da2895b1" />

#### ♦️ show standby brief

<img width="768" height="101" alt="T1-DSW1-show-standby-1" src="https://github.com/user-attachments/assets/79283f88-4335-4ae5-b425-b22ab17d3b45" />

## 🔵 Part B - Configure DSW2 (HSRP Standby + STP Secondary Root)

## 1️⃣ Make DSW2 the STP Secondary Root for VLAN 10

#### ♦️ On **DSW2** (Global Config Mode):

```bash
spanning-tree vlan 10 root secondary
```

Note: This configures DSW2 as the backup STP root, ready to take over if DSW1 fails.

## 2️⃣ Enable HSRP Version 2 on VLAN 10 SVI

```bash
interface vlan 10
standby version 2
```

### 3️⃣ Configure HSRP virtual IP for VLAN 10

```bash
standby 10 ip 10.0.10.200
```

Note: The Virtual IP (VIP) is the default gateway used by hosts in VLAN 10

### 4️⃣ Make DSW2 the Standby router

```bash
standby 10 priority 80
```

Note: by defaulut the priority is 100, 80 is lower than 100 so it becomes the standby router 

### 5️⃣ Configure Preemption

```bash
standby 10 preempt
```

## ✅ Verify on DSW2

#### ♦️ show spanning-tree vlan 10

<img width="840" height="358" alt="T1-DSW2-HSRP-VLAN10-Log" src="https://github.com/user-attachments/assets/48f007b8-c387-4f84-9fde-031ac2e444b9" />

#### ♦️ show standby brief

<img width="788" height="100" alt="T1-DSW2-show-standby-1" src="https://github.com/user-attachments/assets/35776ff6-0c10-4c1e-8ba4-151d6ce38af2" />


