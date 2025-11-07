# DTP & VTP Lab. Task 3

## 🎯 Objective
Configure **SW2** in **VTP Transparent Mode**, create **VLAN 40**, and verify whether VLAN 40 is added to the VLAN database of **SW1** and **SW3**.


## Topology For Reference
<img width="642" height="304" alt="Topology" src="https://github.com/user-attachments/assets/2c7ec9fb-46be-43c9-9715-8c7ff7954117" />

<br>
  
# 🧩  SW2 Configuration (VTP Transparent Mode)

## 1️⃣ Enter global configuration mode:
```bash
enable
configure terminal
```

## 2️⃣ Configure SW2 to operate in VTP Transparent Mode
```bash
vtp mode transparent
```

**Expected Output ✅:**

<img width="467" height="61" alt="T3-SW3-transparent" src="https://github.com/user-attachments/assets/575acad4-45a3-4da6-9850-3b0039bbe672" />

Verify the current VTP status:

## 3️⃣ Create VLAN 40 and assign a name:
```bash
vlan 40
name vlan40
exit
```

## 4️⃣ Save configuration:
```bash
end
write memory
```

<br>

# 🧩 SW1 Verification (VTP Server)

## 1️⃣ Enter global configuration mode:

```bash
enable
```

## 2️⃣ Check VLAN database for VLAN 40:
```bash
show vlan brief
```

**Expected Output ✅:**

<img width="812" height="346" alt="T3-SW1-check-VLAN" src="https://github.com/user-attachments/assets/5d2a667c-4687-423d-86f0-728b247f6f06" />


**Note:** VLAN 40 should not appear on SW1, since VTP Transparent mode does not propagate VLAN changes


<br>

# 🧩 SW3 Verification (VTP Client)

## 1️⃣ Enter global configuration mode:

```bash
enable
```

## 2️⃣ Check VLAN database for VLAN 40:
```bash
show vlan brief
```

**Expected Output ✅:**

<img width="807" height="338" alt="T3-SW3-check-VLAN" src="https://github.com/user-attachments/assets/047ef2cb-a124-4391-9dc0-96e0e5227126" />

**Note:** VLAN 40 should not appear on SW3, since VTP Transparent mode does not propagate VLAN changes









