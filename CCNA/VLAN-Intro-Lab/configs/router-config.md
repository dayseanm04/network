# Router Configuration – VLAN intro Lab

## 📘 Overview
This file provides the IP addressing details and router configuration for VLANs 10, 20, and 30 used in the VLAN Intro Lab.
Each VLAN is configured with its own subnet, default gateway, and connected PCs, with the router handling inter-VLAN communication.

---

## 🔌 Physical Connections

| Connection | From Device/Port     | To Device/Port           | Cable Type              |
|:------------|:---------------------|:--------------------------|:------------------------|
| 1           | R1 GigabitEthernet0/0 | SW1 GigabitEthernet0/1   | Copper Straight-Through |
| 2           | R1 GigabitEthernet0/1 | SW1 GigabitEthernet1/1   | Copper Straight-Through |
| 3           | R1 GigabitEthernet0/2 | SW1 GigabitEthernet2/1   | Copper Straight-Through |

---

## ⚙️ Router Configuration (R1)

### Interface Assignments
| VLAN  | Router Interface     | IP Address    | Subnet Mask        | Description         |
|:------|:---------------------|:--------------|:------------------|:--------------------|
| 10    | GigabitEthernet0/0   | 10.0.0.62     | 255.255.255.192   | VLAN10 Gateway      |
| 20    | GigabitEthernet0/1   | 10.0.0.126    | 255.255.255.192   | VLAN20 Gateway      |
| 30    | GigabitEthernet0/2   | 10.0.0.190    | 255.255.255.192   | VLAN30 Gateway      |

---

### Router CLI — Step by step (use these exact commands on R1)
> **Note:** commands shown with both full form and the shortcut version.

1. Enter privileged EXEC and global configuration mode:
```bash
R1> enable
R1# configure terminal

```

## Configure VLAN 10 interface (GigabitEthernet0/0)

```bash
R1(config)# interface GigabitEthernet0/0
# shortcut: R1(config)# int g0/0

R1(config-if)# ip address 10.0.0.62 255.255.255.192
R1(config-if)# no shutdown
R1(config-if)# exit
```

## Configure VLAN 20 interface (GigabitEthernet0/1)

```bash
R1(config)# interface GigabitEthernet0/1
# shortcut: R1(config)# int g0/1

R1(config-if)# ip address 10.0.0.126 255.255.255.192
R1(config-if)# no shutdown
R1(config-if)# exit
```

## Configure VLAN 30 interface (GigabitEthernet0/2)

```bash
R1(config)# interface GigabitEthernet0/2
# shortcut: R1(config)# int g0/2

R1(config-if)# ip address 10.0.0.190 255.255.255.192
R1(config-if)# no shutdown
R1(config-if)# exit
```

## Verfiy R1 interface configuration
**Command Used:**
```bash
show ip interface brief
```
<img width="821" height="132" alt="show-r1-int" src="https://github.com/user-attachments/assets/0709f54e-52de-46de-9500-2072e8a75c0c" />


## Save the configuration
```bash
R1(config)# end
R1# write memory
# or: R1# copy running-config startup-config
```
