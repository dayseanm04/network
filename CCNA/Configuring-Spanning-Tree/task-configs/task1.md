# 🧪 Task 1: Verify the STP Topology (Step-by-Step)

**Objective:** Use the CLI to check the current STP topology, identify the **root bridge** and the **STP port roles/states** for VLANs 1 and 2.

## 🔌 Enter Privileged EXEC Mode
Do this on **each switch** (SW1, SW2, SW3, SW4):

**Command:**
```bash
enable
```

## 🖥️ 1. Check STP on SW1

**Command:**
```bash
show spanning-tree
```

### ✅ Expexted output for VLAN 1:

<img width="789" height="363" alt="SW1-show-stp-1" src="https://github.com/user-attachments/assets/2867b92b-4652-4130-8457-a57f21608e18" />

### ✅ Expexted output for VLAN 2:

<img width="731" height="350" alt="SW1-show-stp-2" src="https://github.com/user-attachments/assets/55953dc4-580e-4d04-868c-bb372bac32c1" />


**Note:** I used the shortcut version of the command `show spanning-tree`

### Summary output for VLAN1 & 2
|Port|role / state|
|----|------------|
|F0/1|❌ Non-designated, Blocking|
|F0/2|✅ Designated, Forwarding|
|F0/3| ⭐ Root Port, Forwarding|

---

## 🖥️ 2. Check STP on SW2

**Command:**
```bash
show spanning-tree
```

### ✅ Expexted output for VLAN 1:

<img width="782" height="351" alt="SW2-show-stp-1" src="https://github.com/user-attachments/assets/2d62919a-1ac4-43f6-9d5c-3a072df333d6" />

### ✅ Expexted output for VLAN 2:

<img width="750" height="329" alt="SW2-show-stp-2" src="https://github.com/user-attachments/assets/7216b997-3393-4823-b9a6-adf16464d6d4" />

### Summary output for VLAN1 & 2
|Port|role / state|
|----|------------|
|F0/1|✅ Designated, Forwarding|
|F0/2|✅ Designated, Forwarding|
|F0/3|✅ Designated, Forwarding|

---

## 🖥️ 3. Check STP on SW3

**Command:**
```bash
show spanning-tree
```

### ✅ Expexted output for VLAN 1:

<img width="783" height="358" alt="SW3-show-stp-1" src="https://github.com/user-attachments/assets/2b400d3e-69e7-41fe-8f4d-a4531b7049f1" />

### ✅ Expexted output for VLAN 2:

<img width="801" height="333" alt="SW3-show-stp-2" src="https://github.com/user-attachments/assets/5d72589d-e51f-4ed4-b9e1-e342605f42b7" />


