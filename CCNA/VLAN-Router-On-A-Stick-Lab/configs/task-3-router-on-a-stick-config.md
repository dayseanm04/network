# Task 3 - Router-on-a-Stick Configuration

## Topology For Reference
<img width="748" height="409" alt="reference-topology-2" src="https://github.com/user-attachments/assets/291e0e52-717c-4e77-af01-717b6e91d7b3" />

<br/>

---

## 🧩 Objective
Enable **inter-VLAN communication** by:
1. Creating a trunk between **SW2** and the **router (R1)**.  
2. Configuring router subinterfaces for VLANs 10, 20, and 30 using **Router-on-a-Stick (ROAS)**.

---

## ⚙️ Topology Summary

| Device | Interface | Connected To | Purpose | VLANs Allowed | Native VLAN |
|---------|------------|---------------|----------|----------------|--------------|
| SW2 | g0/2 | R1 g0/0 | Trunk link to router | 10, 20, 30 | 100 |
| R1 | g0/0 (subinterfaces) | SW2 g0/2 | Inter-VLAN routing | 10, 20, 30 | 100 |

---

## 🖥️ SW2 Trunk Configuration (to Router)

### 1️⃣ Enter privileged and configuration mode
```bash
enable
configure terminal
```

## 2️⃣ Select the interface connected to the router
```bash
interface g0/2
 description Trunk link to Router R1
```

## 3️⃣ Configure trunk mode
```bash
switchport mode trunk
```

## 4️⃣ Allow VLANs 10, 20, and 30 on the trunk
```bash
switchport trunk allowed vlan 10,20,30
```

## 5️⃣ Configure the native VLAN
```bash
switchport trunk native vlan 100
```

## 6️⃣ Verify configuration
```bash
do show interfaces trunk
```

## ✅ Expected Output
<img width="718" height="324" alt="sw-g2" src="https://github.com/user-attachments/assets/44318814-d038-4a21-9bd5-1bd11857d35b" />
<br/>

# 🖥️ Router Configuration (R1)
🧠 Purpose: The router’s GigabitEthernet0/0 interface will act as a single physical connection to the switch, but it will be divided into three subinterfaces one for each VLAN.

Each subinterface:
- Uses encapsulation dot1q <VLAN number>
- Is assigned the gateway IP address (last usable of each subnet)

### 1️⃣ Enter privileged and configuration mode
```bash
enable
configure terminal
```

## 2️⃣ Enable main interface (ensure it’s up)
```bash
interface g0/0
 no shutdown
 exit
```

## 3️⃣ Configure VLAN 10 subinterface
```bash
interface g0/0.10
 encapsulation dot1q 10
 ip address 10.0.0.62 255.255.255.192
 description VLAN10 Gateway
 exit
```

## 4️⃣ Configure VLAN 20 subinterface
```bash
interface g0/0.20
 encapsulation dot1q 20
 ip address 10.0.0.126 255.255.255.192
 description VLAN20 Gateway
 exit
```
## 5️⃣ Configure VLAN 30 subinterface
```bash
interface g0/0.30
 encapsulation dot1q 30
 ip address 10.0.0.190 255.255.255.192
 description VLAN30 Gateway
 exit
```

## 6️⃣ Verify configuration
```bash
do show ip interface brief
do show ip route
```

## ✅ Expected Output
### show ip route output:
<img width="810" height="333" alt="r1-route-verification" src="https://github.com/user-attachments/assets/413c7009-7e61-493e-95da-87b832e49622" />
- You should see all the subinterfaces connected

### do show ip interface brief:
<img width="834" height="184" alt="R1-ip-int" src="https://github.com/user-attachments/assets/43f09975-ad90-470a-a29b-0c63de1a4fc0" />

- You should see the subinterfaces (g0/0.10, g0/0.20, g0/0.30) is up/up
