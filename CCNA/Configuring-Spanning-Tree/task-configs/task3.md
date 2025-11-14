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
show spanning-tree
```

