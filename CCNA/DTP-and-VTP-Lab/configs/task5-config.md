# DTP & VTP Lab. Task 5


## 🎯 Objective
Configure all switchports connected to hosts as **access ports**, assign them to the correct VLANs, and verify that **DTP** is **disabled** on these ports.

---

## Topology For Reference
<img width="642" height="304" alt="Topology" src="https://github.com/user-attachments/assets/2c7ec9fb-46be-43c9-9715-8c7ff7954117" />

<br>

---

## 🗂️ VLAN & Host Information

| VLAN | Subnet | Connected PCs | Switch / Interfaces |
|------|---------|----------------|----------------------|
| VLAN 10 | 10.0.0.0/26 | PC1, PC2, PC5 | SW1 (F0/1–2), SW3 (F0/1) |
| VLAN 20 | 10.0.0.64/26 | PC8, PC9 | SW1 (F0/3), SW3 (F0/4) |
| VLAN 30 | 10.0.0.128/26 | PC6, PC7 | SW3 (F0/2–3) |
| VLAN 40 | 10.0.0.192/26 | PC3, PC4 | SW2 (F0/1–2) |

---

# 🧩 SW1 Configuration

## 1️⃣ Enter global configuration mode:
```bash
enable
configure terminal
```

## 2️⃣ Configure ports F0/1 and F0/2 for VLAN 10:
```bash
interface range F0/1 - 2
switchport mode access
switchport access vlan 10
exit
```

## 3️⃣ Configure port F0/3 for VLAN 20:
```bash
interface 0/3
switchport mode access
switchport access vlan 20
exit
```

## 4️⃣ Verify VLAN assignments:
```bash
do show vlan brief
```

**Expected output ✅:**

<img width="809" height="240" alt="T5-SW1-vlan" src="https://github.com/user-attachments/assets/d5891c09-180c-4292-a864-0219699e69fb" />


## 5️⃣ Save configuration:
```bash
end
write memory
```

# 🧩 SW2 Configuration

## 1️⃣ Enter global configuration mode:
```bash
enable
configure terminal
```

## 2️⃣ Configure ports F0/1 and F0/2 for VLAN 40:
```bash
interface range F0/1 - 2
switchport mode access
switchport access vlan 40
end
```

## 3️⃣ Verify VLAN assignments:
```bash
show vlan brief
```

**Expected output✅:**

<img width="807" height="268" alt="T5-SW2-vlan" src="https://github.com/user-attachments/assets/fdc35336-d87f-4f24-b75f-955138f1a43e" />



## 4️⃣ Save configuration:
```bash
end
write memory
```

# 🧩 SW3 Configuration

## 1️⃣ Enter global configuration mode:
```bash
enable
configure terminal
```

## 2️⃣ Configure F0/1 for VLAN 10:
```bash
interface F0/1
switchport mode access
switchport access vlan 10
exit
```

## 3️⃣ Configure F0/2 and F0/3 for VLAN 30:
```bash
interface range F0/2 - 3
switchport mode access
switchport access vlan 30
exit
```

## 4️⃣ Configure F0/4 for VLAN 20:
```bash
interface FastEthernet0/4
switchport mode access
switchport access vlan 20
exit
```

## 5️⃣ Verify VLAN assignments:
```bash
do show vlan brief
```

**Expected output ✅:**

<img width="807" height="245" alt="T5-SW3-vlan" src="https://github.com/user-attachments/assets/f8006531-0c56-4242-9a70-bddfadae3a3d" />

# Verification DTP status

## 1️⃣ Check SW1 DTP status in global config mode:
```bash
show dtp status
```

**Expected output ✅:**

<img width="507" height="117" alt="T5-SW1-dtp-verify" src="https://github.com/user-attachments/assets/311ef93b-3a7a-436d-afdb-77c6bb94e1ce" />

## 2️⃣ Check SW2 DTP status in global config mode:
```bash
show dtp status
```

**Expected output ✅:**

<img width="504" height="115" alt="T5-SW2-dtp-verify" src="https://github.com/user-attachments/assets/34ca1058-5a51-41a9-9c94-454ba79505aa" />

## 3️⃣ Check SW3 DTP status in global config mode:

```bash
show dtp status
```

**Expected output ✅:**

<img width="549" height="115" alt="T5-SW3-dtp-verify" src="https://github.com/user-attachments/assets/ab6a017c-5525-4445-9927-d83223cea03f" />
