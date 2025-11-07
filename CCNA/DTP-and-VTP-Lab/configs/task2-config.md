# DTP & VTP Lab. Task 2

## 🎯 Objective
Configure **SW1** as the **VTP Server** in domain `CCNA`, create VLANs **10**, **20**, and **30**, and verify if the VLANs propagate to **SW2** and **SW3**.

## Topology For Reference
<img width="642" height="304" alt="Topology" src="https://github.com/user-attachments/assets/2c7ec9fb-46be-43c9-9715-8c7ff7954117" />

# 🧩 SW1 Configuration (VTP Server)


## 1️⃣ Enter global configuration mode:
```bash
enable
configure terminal
```

## 2️⃣ View current VTP status
```bash
do show vtp status
```

**Expected output ✅:**

<img width="669" height="244" alt="T2-SW1-vtp-stat" src="https://github.com/user-attachments/assets/c0a87773-c2d5-43bc-8664-28b3e99c0fff" />


## 3️⃣ Configure the switch in VTP domain CCNA:
```bash
vtp domain CCNA
```

**Expected output ✅:**

<img width="508" height="71" alt="T2-SW1-vtp-domain" src="https://github.com/user-attachments/assets/ae7120fe-734e-4368-b493-51041a2cdee2" />


## 4️⃣ Create VLANs and assign names:
```bash
vlan 10
name vlan10
exit

vlan 20
name vlan20
exit

vlan 30
name vlan30
exit
```

## 5️⃣ Verify VLANs are created:
```bash
do show vlan brief
```

**Expected output ✅:**

<img width="818" height="333" alt="T2-SW1-vlan-verify" src="https://github.com/user-attachments/assets/6fbf5771-ab0e-4257-bd96-a43245b9e542" />

## 6️⃣ Verify updated VTP status:
```bash
do show vtp status
```

**Expected output ✅:**

<img width="749" height="226" alt="T2-SW1-vtp-stat-again" src="https://github.com/user-attachments/assets/1ad461cd-1700-4f12-b61b-f2844bc2270f" />


## 7️⃣ Save the configuration:

```bash
end
write memory
```

<br>

# 🧩 SW2 Verification

## 1️⃣ Enter privileged EXEC mode:

```bash
enable
```

## 2️⃣ Verify VLANs were received from SW1:
```bash
show vlan brief
```

**Expected output ✅:**

<img width="817" height="321" alt="T2-SW2-check-VLAN" src="https://github.com/user-attachments/assets/dcce196f-cccf-4800-95e3-c496784aa653" />


<br>
<br>

# 🧩 SW3 Verification

## 1️⃣ Enter privileged EXEC mode:

```bash
enable
```

## 2️⃣ Verify VLANs were received from SW1:
```bash
show vlan brief
```

**Expected output ✅:**

<img width="809" height="338" alt="T2-SW3-check-VLAN" src="https://github.com/user-attachments/assets/3fd2b7ce-7f08-4c88-b45d-6221b99cf485" />
