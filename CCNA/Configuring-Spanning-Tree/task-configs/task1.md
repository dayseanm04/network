# 🧪 Task 1: Verify the STP Topology (Step-by-Step)

**Objective:** Use the CLI to check the current STP topology, identify the **root bridge** and the **STP port roles/states** for VLANs 1 and 2.

## 🔌 Enter Privileged EXEC Mode
Do this on **each switch** (SW1, SW2, SW3, SW4):

**Command:**
```bash
enable
```

## 🖥️ 1. Check STP on SW1
```bash
show spanning-tree
```

### ✅ Expexted output for VLAN 1:

<img width="789" height="363" alt="SW1-show-stp-1" src="https://github.com/user-attachments/assets/2867b92b-4652-4130-8457-a57f21608e18" />

### ✅ Expexted output for VLAN 2:

<img width="731" height="350" alt="SW1-show-stp-2" src="https://github.com/user-attachments/assets/55953dc4-580e-4d04-868c-bb372bac32c1" />


**Note:** I used the shortcut version of the command `show spanning-tree`

### Summanry output for VLAN1 & 2
|Port|role / state|
|----|------------|
|F0/1|❌ Non-designated, Blocking|
|F0/2|❌ ✅ Designated, Forwarding|
|F0/3| ⭐ Root Port, Forwarding|

---

## 🖥️ 2. Check STP on SW2
```bash
show spanning-tree
```
