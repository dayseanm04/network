# 🔁 Task2 Synchronize HSRP and STP for VLAN 20

## 📌 Objective

Synchronize **HSRP** and **STP** roles for **VLAN 20** so that:
- **DSW2** is the **HSRP Active Gateway** and **STP Root Bridge**
- **DSW1** is the **HSRP Standby Gateway** and **STP Secondary Root**

This alignment ensures hosts in VLAN 20 use the **most direct path** to their default gateway.

## Topology For Reference

<img width="618" height="332" alt="Topology" src="https://github.com/user-attachments/assets/67061080-b132-4e96-a33b-6c05489f583e" />

---

## 📋 VLAN 20 HSRP Configs

| Setting | Value |
|------|------|
| HSRP Version | 2 |
| HSRP Group | 20 |
| Virtual IP (VIP) | 10.0.20.200 |
| DSW2 Priority | 120 |
| DSW1 Priority | 80 |
| Preempt | Enabled |

---

# 🟢 Part A - Configure DSW2 (HSRP Active + STP Root)

## 1️⃣ Make DSW1 the STP Root for VLAN 20

#### ♦️ On **DSW2** (Global Config Mode):

```bash
spanning-tree vlan 20 root primary
```

## 2️⃣ Enable HSRP Version 2 on VLAN 20 SVI

```bash
interface vlan 20
standby version 2
```

### 3️⃣ Configure HSRP virtual IP for VLAN 20

```bash
standby 20 ip 10.0.20.200
```

### 4️⃣ Make DSW2 the Active router

```bash
standby 20 priority 120
```

Note: by defaulut the priority is 100, 120 is higher than 100 so it becomes the active router 

### 5️⃣ Configure Preemption

```bash
standby 20 preempt
```

Note: preempt allows DSW2 to take back the Active role if it comes back online after a failure

## ✅ Verify on DSW2

#### ♦️ show spanning-tree vlan 20

<img width="857" height="334" alt="T2-DSW2-show-stp-vlan20" src="https://github.com/user-attachments/assets/d471a7ec-87f5-42ae-823d-2848ad2a8cfe" />

Note: DSW2 is the Root Bridge for Vlan 20


#### ♦️ show standby brief

<img width="768" height="134" alt="T2-DSW2-show-standby-1" src="https://github.com/user-attachments/assets/bc5b405f-3721-4d93-a22e-93ef511c3326" />

Note: DSW2 is the Active router for VLAN 20

## ✅ Verify on DSW1

#### ♦️ show spanning-tree vlan 20

<img width="793" height="386" alt="T2-DSW1-show-stp-vlan20" src="https://github.com/user-attachments/assets/afd7026f-edac-488c-9a29-623a6732207a" />

Note: DSW1 is the secondary root bridge for Vlan 20 because its G1/0/3 is a root port connected to DSW2

### ♦️ show standby brief

<img width="786" height="132" alt="T2-DSW1-show-standby-1" src="https://github.com/user-attachments/assets/184439e6-41b5-477a-bcc2-10240b290985" />

Note: DSW1 is the Standby router for vlan 20
