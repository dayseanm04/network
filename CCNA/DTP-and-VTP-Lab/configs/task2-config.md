# DTP & VTP Lab. Task2


## 🎯 Objective
Configure **SW1** as the **VTP Server** in domain `CCNA`, create VLANs **10**, **20**, and **30**, and verify if the VLANs propagate to **SW2** and **SW3**.

---

# 🧩 SW1 Configuration (VTP Server)

## 1️⃣ Enter global configuration mode:
```bash
enable
configure terminal
```

## 2️⃣ do show vtp status
```bash
do show vtp status
```

**Expected output ✅**

<img width="665" height="239" alt="T2-SW1-vtp-stat" src="https://github.com/user-attachments/assets/e72af45b-8c84-41e8-989a-be76e9b3ebce" />

## 3️⃣ Configure the switch in VTP domain CCNA:
```bash
vtp domain CCNA
```

**Expected output ✅**

<img width="505" height="68" alt="T2-SW1-vtp-domain" src="https://github.com/user-attachments/assets/e3f44622-b28c-4d4f-bd65-ba214fc5d008" />


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

**Expected output ✅**
<img width="816" height="329" alt="T2-SW1-vlan-verify" src="https://github.com/user-attachments/assets/8105af77-0a89-4946-ba61-080bb2b09036" />

## 6️⃣ Verify updated VTP status:
```bash
do show vtp status
```

**Expected output ✅**

<img width="745" height="223" alt="T2-SW1-vtp-stat-again" src="https://github.com/user-attachments/assets/6d7101de-7ae1-4735-a419-d0232e689d3e" />


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

**Expected output ✅**

<img width="813" height="318" alt="T2-SW2-check-VLAN" src="https://github.com/user-attachments/assets/9b4ec6fe-68de-4a25-943f-0d99b2445ff4" />

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

**Expected output ✅**

<img width="805" height="332" alt="T2-SW3-check-VLAN" src="https://github.com/user-attachments/assets/0ffa6a0f-1ae3-4319-be83-f89d9362461b" />



