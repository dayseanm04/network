# Task 1: SW2 VLAN Configuration

## Purpose
Configure VLANs and assign access ports on **Switch SW2**:
- VLAN 10 → access ports f0/2, f0/3
- VLAN 20 → access port f0/1

---

## 1) Enter privileged and global config mode
```bash
enable
configure terminal
```

## 2) Optional view IP interfaces
```bash
do show ip interface brief
do show interfaces status
```

## 3) Create / name VLANs (recommended)
```bash
vlan 10
 name VLAN_10_Engineering
exit

vlan 20
 name VLAN_20_HR
exit
```

## 4) Verify the VLANs has been created
```bash
do show vlan brief
```

## 5) Assign ports to VLAN 10 (PCs on VLAN10)
```bash
interface range f0/2 , f0/3
 description VLAN10 -- PCs
 switchport mode access
 switchport access vlan 10
 exit
```

## 5) Assign ports to VLAN 20 (PCs on VLAN20)
```bash
interface f0/1
 description VLAN20 -- PCs
 switchport mode access
 switchport access vlan 20
 exit
```

## 6) Save config
```bash
end
write memory
```

## 6) Verification

```bash
show vlan brief
show interfaces status
```
