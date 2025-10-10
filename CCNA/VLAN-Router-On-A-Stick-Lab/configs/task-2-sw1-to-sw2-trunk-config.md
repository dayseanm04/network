# Task 2 - SW1-to-SW2 Trunk Configuration

> Step-by-step guide for configuring trunk links between SW1 and SW2.  

---
## Topology For Reference
<img width="697" height="372" alt="reference-topology" src="https://github.com/user-attachments/assets/c64869de-2df8-4dec-b6bf-800a227522ee" />
<br/>


## 🧩 Objective
Create a trunk link between **Switch 1 (SW1)** and **Switch 2 (SW2)** that carries VLAN 10 and VLAN 30, with a **Native VLAN of 100**.  
This trunk allows VLAN traffic to pass between switches.

---

## ⚙️ Topology Summary
| Device | Trunk Interface | Connected To | Allowed VLANs | Native VLAN |
|---------|----------------|---------------|----------------|--------------|
| SW1 | GigabitEthernet0/1 | SW2 G0/1 | 10, 30 | 100 |
| SW2 | GigabitEthernet0/1 | SW1 G0/1 | 10, 30 | 100 |

---

## 🖥️ SW1 Trunk Configuration

### 1️⃣ Enter privileged and configuration mode
```bash
enable
configure terminal
```

### 2️⃣ Select trunk interface (connected to SW2)
```bash
interface g0/1
 description Trunk link to SW2
```

### 3️⃣ Configure trunk mode
```bash
switchport mode trunk
```
> Note: Some older switches may require encapsulation type configuration before setting trunk mode. IF prompted use:

```bash
switchport trunk encapsulation dot1q
```

### 4️⃣ Allow only specific VLANs on the trunk
```bash
switchport trunk allowed vlan 10,30
```

### 5️⃣ Configure the native VLAN
```bash
switchport trunk native vlan 100
```

### 6️⃣ Verify configuration
```bash
do show interfaces trunk
```

✅ **Expected output:** <br/>
<img width="689" height="223" alt="sw1-expectedd-trunk-output" src="https://github.com/user-attachments/assets/71898dca-f803-452d-9953-70043bba6893" />


## 🖥️ SW2 Trunk Configuration

### 1️⃣ Enter privileged and configuration mode
```bash
enable
configure terminal
```

### 2️⃣ Select trunk interface (connected to SW1)
```bash
interface g0/1
 description Trunk link to SW2
```

### 3️⃣ Configure trunk mode
```bash
switchport mode trunk
```
### 4️⃣ Allow only specific VLANs on the trunk
```bash
switchport trunk allowed vlan 10,30
```
### 5️⃣ Configure the native VLAN
```bash
switchport trunk native vlan 100
```

<img width="712" height="235" alt="vlan30-not-in-management-domain" src="https://github.com/user-attachments/assets/caf11ae1-2c51-4c41-8844-7ff8180905c4" />
<br/>
do show interfaces trunk dosent show VLAN30 in the active in management domain because theres no VLAN30 on SW2.

#### Create VLAN30 on SW2
```bash
vlan 30
name VLAN_30_Sales
exit
```

### 6️⃣ Verify configuration
```bash
do show interfaces trunk
```

✅ **Expected output:** <br/>
<img width="710" height="307" alt="sw2-expectedd-trunk-output" src="https://github.com/user-attachments/assets/a649102a-31ff-4f38-a8f4-37b6784d3986" />
<br/>
Note: You will not see the Gi0/2 interface beacause I configured it earlier(Config will be in Task3). Gig0/2 is the interface connected to the router. <br/>
But you should see the Gig0/1 interface


## Checklist:
- g0/1 is trunking on both switches
- VLANs 10 & 30 are active and allowed
- Native VLAN 100 matches on both ends

## 🧠 Notes
- Always make sure the native VLANs match both trunk ends. Native VLAN mismatch can connectivity issues.
- Only allowed required VLANs on the trunk to maintain security and efficiency.
- If you later connect the router (Task 3), ensure VLAN 10, 20, 30 are all trunked on SW2 ↔ Router link.
- Because All of the VLANs need to able to reach the router for it to route traffic to other VLANs
