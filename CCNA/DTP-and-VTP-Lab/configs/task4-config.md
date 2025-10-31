# DTP & VTP Lab. Task 4


## 🎯 Objective
Configure **SW3** in **VTP Client Mode** and attempt to create **VLAN 50**.  
Verify whether VLAN 50 is added to the VLAN database.

---

# 🧩 SW3 Configuration (VTP Client Mode)

## 1️⃣ Enter privileged and global configuration mode:
```bash
enable
configure terminal
```

## 2️⃣ Set SW3 to VTP Client Mode:
```bash
vtp mode client
```

**Expected Output ✅:**

<img width="475" height="63" alt="T4-vtp-client" src="https://github.com/user-attachments/assets/04107175-e6c7-4832-83ae-887908b5ebfe" />

## 3️⃣ Attempt to create VLAN 50:
```bash
vlan 50
```

**Expected Output ✅:**

<img width="661" height="61" alt="T4-vlan50" src="https://github.com/user-attachments/assets/6a406ad6-949b-4263-b305-d4ac8442981b" />

**Note:** Cannot configure vlan 50 because SW3 is in client mode, so to configure VLAN 50 on SW3, you have too configure it on SW1, which will then sync the VLAN database.
