# 🖧 Switch Configuration – VLAN Intro Lab

## 📘 Overview
This configuration file shows the VLAN setup, port assignments, and verification commands for **Switch SW1** in the **Intro to VLAN Lab**.  
The switch is configured with VLANs 10, 20, and 30, each assigned to specific interfaces connected to PCs and the router (R1).

---

## 🔌 Physical Connections

| Connection | From Device/Port       | To Device/Port           | Cable Type              |
|:-----------|:-----------------------|:--------------------------|:------------------------|
| 1          | SW1 GigabitEthernet0/1 | R1 GigabitEthernet0/0     | Copper Straight-Through |
| 2          | SW1 GigabitEthernet1/1 | R1 GigabitEthernet0/1     | Copper Straight-Through |
| 3          | SW1 GigabitEthernet2/1 | R1 GigabitEthernet0/2     | Copper Straight-Through |

---

## ⚙️ VLAN Configuration Steps

## Step 1: Enter Global Configuration Mode
```bash
enable
configure terminal
```

## Step 2: Create VLANs
```bash
vlan 10
 name Engineering
exit

vlan 20
 name HR
exit

vlan 30
 name Sales
exit
```

## Step 3: Assign Ports to VLANs

### Assign VLAN 10 to the ports connected to PCs in VLAN 10 and router interface G0/0.

```bash
interface range g0/1, f3/1, f4/1
 switchport mode access
 switchport access vlan 10
exit
```

### Assign VLAN 20 to the ports connected to PCs in VLAN 20 and router interface G0/1.

```bash
interface range g1/1, f5/1, f6/1
 switchport mode access
 switchport access vlan 20
exit
```

### Assign VLAN 30 to the ports connected to PCs in VLAN 30 and router interface G0/2.

```bash
interface range g2/1, f7/1, f8/1
 switchport mode access
 switchport access vlan 30
exit
```

## 🔎 Verification: After completing the configuration, verify VLAN creation and port assignments.
### Check VLANs

<img width="788" height="237" alt="vefify VLAN config" src="https://github.com/user-attachments/assets/14eec748-b538-48ca-8bdf-41603372d10c" />
<br/>

**Expected Output**
- You should see VLAN 10 (Engineering), VLAN 20 (HR), and VLAN 30 (Sales).
- You should also see the ports for the VLANs.
