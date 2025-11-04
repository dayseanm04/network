# Task 1 — SW1 VLAN Configuration
> Step-by-step switch config for Task 1 (SW1) — VLAN 10 and VLAN 30

## Purpose
Configure VLANs and assign access ports on **Switch SW1**:
- VLAN 10 → access ports f0/1, f0/2
- VLAN 30 → access ports f0/3, f0/4

---

## 1) Enter privileged and global config mode
```bash
enable
configure terminal
```

## 2) Optional view ip interfaces
```bash
do show ip interface brief
do show interfaces status
```

## 3) Create / name VLANs (recommended)
```bash
vlan 10
 name VLAN_10_Engineering
exit

vlan 30
 name VLAN_30_Sales
exit
```
## 4) Verify the VLANs has been created
```bash
do show vlan brief
```

## 5) Assign ports to VLAN 10 (PCs on VLAN10)
```bash
interface range f0/1 , f0/2
 description VLAN10 -- PCs
 switchport mode access
 switchport access vlan 10
 exit
```

## 5) Assign ports to VLAN 30 (PCs on VLAN30)
```bash
interface range f0/3 , f0/4
 description VLAN30 -- PCs
 switchport mode access
 switchport access vlan 30
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

# If you want to verify the port switchport details:
show interfaces f0/1 switchport
show interfaces f0/3 switchport
```
