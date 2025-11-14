# 🏛️ Task 2: Configure Primary & Secondary Root Bridges (PVST+)

**Objective:** Configure SW1 and SW2 so that each switch becomes the **primary** and **secondary** root bridge for different VLANs. This creates **load balancing** across VLAN 1 and VLAN 2.

---

## 🎯 Goal
- SW1 → **Primary Root for VLAN 1**, **Secondary Root for VLAN 2**  
- SW2 → **Primary Root for VLAN 2**, **Secondary Root for VLAN 1**

This allows traffic for different VLANs to take different paths. 🔀

---

## 🛠️ Step 1: Configure SW1

Enter global configuration mode:

```bash
enable
configure terminal
```

## 📌 Configure SW1 as the Primary Root for VLAN 1:
```bash
spanning-tree vlan 1 root primary
```

## 📌 Configure SW1 as the Secondary Root for VLAN 2:
```bash
spanning-tree vlan 2 root secondary
```

## 🛠️ Step 2: Configure SW2

Enter global configuration mode:

```bash
enable
configure terminal
```

## 📌 Configure SW2 as the Primary Root for VLAN 1:
```bash
spanning-tree vlan 2 root primary
```

## 📌 Configure SW2 as the Secondary Root for VLAN 2:
```bash
spanning-tree vlan 1 root secondary
```

## 🔍 Step 3: Verify STP Changes

### On SW1 

```bash
show spanning-tree
```

### Expected output For VLAN 1 ✅

<img width="792" height="347" alt="T2-SW1-V1" src="https://github.com/user-attachments/assets/c30e5776-d2dd-4e51-88ff-43e641c68e2e" />

### Expected output For VLAN 2 ✅

<img width="713" height="345" alt="T2-SW1-V2" src="https://github.com/user-attachments/assets/ec6e9646-bb9f-4837-bcd2-6a9bb4b7e7e7" />

