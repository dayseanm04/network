# 🏛️ Task 2: Configure Primary & Secondary Root Bridges (PVST+)

**Objective:** Configure SW1 and SW2 so that each switch becomes the **primary** and **secondary** root bridge for different VLANs. This creates **load balancing** across VLAN 1 and VLAN 2.

## 🎯 Goal
- SW1 → **Primary Root for VLAN 1**, **Secondary Root for VLAN 2**  
- SW2 → **Primary Root for VLAN 2**, **Secondary Root for VLAN 1**

This allows traffic for different VLANs to take different paths. 🔀



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

---

## 🔍 Step 3: Verify STP Changes

### On SW1 in Priviliged EXEC mode

```bash
show spanning-tree
```

### Expected output For VLAN 1 ✅

<img width="792" height="347" alt="T2-SW1-V1" src="https://github.com/user-attachments/assets/c30e5776-d2dd-4e51-88ff-43e641c68e2e" />

You should see:
- SW1 is now the Root Bridge for VLAN 1
- Bridge ID Priority around 24577

### Expected output For VLAN 2 ✅

<img width="717" height="349" alt="T2-SW1-V2" src="https://github.com/user-attachments/assets/86ef75e0-2ae9-43a2-b6f3-826e4abbd110" />

You should see:
- SW1 is the secondary root bridge for VLAN 2
- Bridge ID priority around 28674 (higher than the primary bridge ID priority for VLAN 1)

---

### On SW2 in Priviliged EXEC mode

```bash
show spanning-tree
```

### Expected output For VLAN 1 ✅:

<img width="714" height="358" alt="T2-SW2-V1" src="https://github.com/user-attachments/assets/b518ae68-748e-4e5b-b701-506cbd1f3e4e" />

You should see:
- SW2 is now the Secondary Root Bridge for VLAN 1
- Bridge ID Priority around 28673

### Expected output For VLAN 2 ✅:

<img width="717" height="344" alt="T2-SW2-V2" src="https://github.com/user-attachments/assets/65c6af4e-2c69-445d-b365-8279930e260b" />

You should see:
- SW2 is now the Root Bridge for VLAN 2
- Bridge ID Priority around 24578 (lower than the primary bridge ID priority for VLAN 1)

---

✅ Summary of Task 2
- Load balanced for each VLAN: VLAN 1 uses SW1 as the root bridge; VLAN 2 uses SW2 as the bridge.
- Different priorities assigned by Cisco's automatic root primary/secondary commands.
- The switch with the lowest priority becomes the root bridge
- Note in the output of VLAN 2
