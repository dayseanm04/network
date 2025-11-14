# 🔢 Task 4: Change Port Priority on SW1 (VLAN 1)

**Objective:** Increase the **port priority** on SW1’s F0/1 interface for **VLAN 1** and observe whether SW3 selects a different root port.

## Topology For Reference

<img width="454" height="294" alt="Topology" src="https://github.com/user-attachments/assets/72f4a007-e83a-43ed-bb0c-6e4cae158fe3" />

**Objective:** Increase the **port priority** on SW1’s F0/1 interface for **VLAN 1** and observe whether SW3 selects a different root port.

---

## 🛠️ Step 1: Enter Interface Configuration Mode on SW1:

Enter global configuration mode:

```bash
enable
configure terminal
```

**Select interface f0/1:**
```bash
int f0/1
```

## 🧩 Step 2: Change the Port Priority for VLAN 1:
```bash
spanning-tree vlan 1 port-priority 240
```

## 🔍 Step 3: Verify the STP Topology on SW3:
```bash
show spanning-tree
```

**Expected output For VLAN 1 ✅:**

<img width="749" height="360" alt="T4-show-stp-SW3" src="https://github.com/user-attachments/assets/61e20aee-c7b8-4372-9d4b-0546c9dd53e7" />

## 🔍 Step 4: Verify the SW1 F0/1 root cost:
```bash
show spanning-tree
```

<img width="787" height="343" alt="T4-sh-SW1-stp" src="https://github.com/user-attachments/assets/7048d56b-ba04-4631-89d2-c92b53d86fe7" />

### 🧠 Why Didn’t the Root Port Change?
- STP only uses port priority as a tie-breaker if the root path cost are equal.
- In this case, the root path cost did NOT change, so:
  - The port priority configuration had no effect on root port selection.
  - F0/2 still had the lowest overall cost to reach the root bridge.
