# ⚖️ Task 3: Increase STP Cost on SW4 (VLAN 1)

**Objective:** Increase the **STP cost** on SW4’s F0/2 interface for **VLAN 1** and observe whether SW4 selects a different root port.


## 🛠️ Step 1: Enter Interface Configuration Mode on SW4 for F0/2

Enter global config mode:

```bash
configure terminal
```

### Select interface F0/2:
```bash
interface f0/2
```

## 🧩 Step 2: Increase VLAN 1 Cost to 100
```bash
spanning-tree vlan 1 cost 100
```

**Note:** This makes the F0/2 path more expensive, which may change the root port selection. The lowest root cost wins!

## 🔍 Step 3: Verify the New STP Topology

```bash
show spanning-tree detail
```

**Expected output For VLAN 1 ✅:**

<img width="641" height="110" alt="T3-show-stp-detail" src="https://github.com/user-attachments/assets/fb407658-11d1-45ad-80e7-4349057a4e0a" />

```bash
show spanning-tree
```

<img width="787" height="339" alt="T3-SW4-verify" src="https://github.com/user-attachments/assets/b863e67a-5c64-481a-8b22-e93e88ddfa13" />

SW4 selected its F0/1 interface as the new root port, because it has the lowest root cost of 19. A lower root cost is the best path to the root bridge. In case the root cost of SW4 F0/2 interface root cost is 100, which is higher that 19.
