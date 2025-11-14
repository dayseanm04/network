# 🔢 Task 4: Change Port Priority on SW1 (VLAN 1)

**Objective:** Increase the **port priority** on SW1’s F0/1 interface for **VLAN 1** and observe whether SW3 selects a different root port.

## Topology For Reference

<img width="454" height="294" alt="Topology" src="https://github.com/user-attachments/assets/72f4a007-e83a-43ed-bb0c-6e4cae158fe3" />

**Objective:** Increase the **port priority** on SW1’s F0/1 interface for **VLAN 1** and observe whether SW3 selects a different root port.

---

## 🛠️ Step 1: Enter Interface Configuration Mode on SW1

Enter global configuration mode:

```bash
enable
configure terminal
```

**Select interface f0/1**
```bash
int f0/1
```

## 🧩 Step 2: Change the Port Priority for VLAN 1
```bash
spanning-tree vlan 1 port-priority 240
```

## 🔍 Step 3: Verify the STP Topology on SW3
```bash
show spanning-tree
```

