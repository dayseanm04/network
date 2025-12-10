# Task4-Configure-OSPF-Reference-Bandwidth.md


**🎯 Objective:**
Configure the OSPF reference bandwidth on all routers so that a FastEthernet interface has a cost of 100.

## 🛠️ Configure OSPF Reference Bandwidth on R1

### 1️⃣ Enter Global config mode

```bash
enable
conf t
```

### 2️⃣ Enter OSPF configuration mode (process 1)

```bash
router ospf 1
```

### 3️⃣ Set the reference bandwidth to 10000 Mbps

```bash
auto-cost reference-bandwidth 10000
```

**Expected Ouput ✅:**

<img width="799" height="76" alt="T4-R1-log" src="https://github.com/user-attachments/assets/cff04898-0e3c-420b-b516-fcb6351c6304" />

### 4️⃣ Exit back to privileged EXEC mode

```bash
end
```

### 5️⃣ Verify OSPF interface costs

```bash
show ip ospf interface brief
```

**Expected Ouput ✅:**

<img width="964" height="163" alt="T4-R1-show-ospf-int-brief" src="https://github.com/user-attachments/assets/2eec49e3-5829-4921-832f-858e29cfbab8" />



