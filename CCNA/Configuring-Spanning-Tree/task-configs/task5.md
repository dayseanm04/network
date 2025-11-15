# 🛡️ Task 5: Configure PortFast & BPDU Guard on Access Ports

**Objective:** Enable **PortFast** and **BPDU Guard** on the access interfaces (F0/3) of SW3 and SW4, then test BPDU Guard behavior.


## 🛠️ Step 1: Configure SW3 (Interface F0/3)

**Enter configuration mode:**

**Command:**
```bash
enable
configure terminal
```

**Select interface F0/3:** <br/>
**Command:**
```bash
int f0/3
```

## ⚡ Enable PortFast:
**Command:**
```bash
spanning-tree portfast
```

### Expected output:
<img width="735" height="171" alt="T5-portfast-msg" src="https://github.com/user-attachments/assets/36ceacfd-b599-4834-a29d-1378c3308c5d" />


**Note: this warning says portfast should be only enabled on ports connected to a single host such as PC’s. Because enabling portfast on an interface connected to a switch can cause temporary loops.** <br/>

## 🛡️ Enable BPDU Guard:
**Command:**
```bash
spanning-tree bpduguard enable
```

## 🛠️ Step 2: Configure SW4 (Interface F0/3)

**Command:**
```bash
enable
configure terminal
```

**Select interface F0/3:**
**Command:**
```bash
int f0/3
```

## ⚡ Enable PortFast:
**Command:**
```bash
spanning-tree portfast
```

## 🛡️ Enable BPDU Guard:
**Command:**
```bash
spanning-tree bpduguard enable
```
