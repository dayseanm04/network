# DTP & VTP Lab. Task 4


## 🎯 Objective
Configure **SW3** in **VTP Client Mode** and attempt to create **VLAN 50**.  
Verify whether VLAN 50 is added to the VLAN database.

---

## Topology For Reference
<img width="642" height="304" alt="Topology" src="https://github.com/user-attachments/assets/2c7ec9fb-46be-43c9-9715-8c7ff7954117" />


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

<img width="473" height="61" alt="T4-vtp-client" src="https://github.com/user-attachments/assets/1f1479c6-270a-4ece-9134-baa14a25f5f6" />


## 3️⃣ Attempt to create VLAN 50:
```bash
vlan 50
```

**Expected Output ✅:**

<img width="666" height="65" alt="T4-vlan50" src="https://github.com/user-attachments/assets/ac22ce1a-d775-4aa9-aa71-ac01d00699a8" />

**Note:** Cannot configure vlan 50 because SW3 is in client mode, so to configure VLAN 50 on SW3, you have too configure it on SW1, which will then sync the VLAN database.
