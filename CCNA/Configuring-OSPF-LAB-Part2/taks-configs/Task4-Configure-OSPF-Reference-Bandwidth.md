# 🧩 Task 4 - Configure OSPF Reference Bandwidth 

## Topology For Reference

<img width="711" height="341" alt="Topology" src="https://github.com/user-attachments/assets/53e6080d-57be-4f5f-b410-c3046016c538" />

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

## 🛠️ Configure OSPF Reference Bandwidth on R2

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



### 4️⃣ Exit back to privileged EXEC mode

```bash
end
```

### 5️⃣ Verify OSPF interface costs

```bash
show ip ospf interface brief
```

**Expected Ouput ✅:**

<img width="949" height="120" alt="T4-R2-show-ospf-int-brief" src="https://github.com/user-attachments/assets/88c7e315-a93c-44bf-90cc-aead0e334474" />

## 🛠️ Configure OSPF Reference Bandwidth on R3

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


### 4️⃣ Exit back to privileged EXEC mode

```bash
end
```

### 5️⃣ Verify OSPF interface costs

```bash
show ip ospf interface brief
```

**Expected Ouput ✅:**

<img width="932" height="107" alt="T4-R3-show-ospf-int-brief" src="https://github.com/user-attachments/assets/6235f7dc-a144-4e08-921f-2c8d602e694d" />

## 🛠️ Configure OSPF Reference Bandwidth on R4

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


### 4️⃣ Exit back to privileged EXEC mode

```bash
end
```

### 5️⃣ Verify OSPF interface costs

```bash
show ip ospf interface brief
```

**Expected Ouput ✅:**

<img width="927" height="104" alt="T4-R4-show-ospf-int-brief" src="https://github.com/user-attachments/assets/0fb3b869-4a99-41dc-890a-2d2ed324c5a0" />


