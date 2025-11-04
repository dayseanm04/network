# 🧩 Multilayer Switching Lab

# Task 2 Config ⚙️
Step-by-step configuration for **Task 2** -configuring SVIs on the multilayer switch (**SW2**) for inter-VLAN routing.

---

## 🧩 Objective
Configure **SVIs (Switch Virtual Interfaces)** for each VLAN on the multilayer switch and assign the **last usable IP address** of each subnet.

| VLAN | Subnet | Subnet Mask | Last Usable IP (SVI IP) |
|------|---------|--------------|--------------------------|
| 10 | 10.0.0.0/26 | 255.255.255.192 | 10.0.0.62 |
| 20 | 10.0.0.64/26 | 255.255.255.192 | 10.0.0.126 |
| 30 | 10.0.0.128/26 | 255.255.255.192 | 10.0.0.190 |

---

## 1) View VLANs on SW2

### Enter into Privileged EXEC mode

```bash
enable
show vlan brief
```

### Expected Output✅
<img width="845" height="294" alt="sw-vlan-sw2" src="https://github.com/user-attachments/assets/f6e305fa-ee97-41a9-8dcf-9dd3888895e8" />


---

## 2) Create SVIs for each VLAN

Enter global config mode:
```bash
configure terminal
```

1️⃣Create interface for VLAN 10 and assign its IP:
```bash
interface vlan 10
ip address 10.0.0.62 255.255.255.192
```

2️⃣ Create SVI for VLAN 20
```bash
interface vlan 20
ip address 10.0.0.126 255.255.255.192
```

### Expected Output✅
<img width="780" height="96" alt="VLAN20-int-up" src="https://github.com/user-attachments/assets/ba1fd6be-90e4-4317-9c7c-b27205bb54c6" />

Note: it changed Interface VLAN20 state to up so no need to use the `no shutdown` command

3️⃣ Create SVI for VLAN 30
```bash
interface vlan 30
ip address 10.0.0.190 255.255.255.192
```

---
## 3) Verify all SVIs
In Privileged EXEC mode:
```bash
show ip int brief | include Vlan
```

### Expected Output✅
<img width="796" height="115" alt="verify-SVI" src="https://github.com/user-attachments/assets/986b8548-c18d-4a22-8c6c-441dca9cc4cc" />

---

## 4) Save Config
```bash
write memory
```
