# Task1 Configure Serial Link and OSPF.md 🧵🌐


## 🎯 Goal
Configure the **serial connection between R1 and R2** (clock rate **128000**) and enable **OSPF** on the new serial link.

## Topology For Reference

<img width="707" height="307" alt="topololgy" src="https://github.com/user-attachments/assets/5f516c89-9322-44b4-8128-ff659905e275" />

## 🧵 Part A: Configure the Serial Link (R1 ↔ R2)

### ✅ Configure R1 (Serial + Clock Rate)

---

### 1️⃣ global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Enter the serial interface

```bash
interface s0/0/0
```

### 3️⃣ Set the clock rate (128000)

```bash
clock rate 128000
```

### 4️⃣ Configure the IP address

```bash
ip address 192.168.12.1 255.255.255.252
```

### 5️⃣ Enable the interface

```bash
no shutdown
```

**Expected Output ✅:**

<img width="635" height="66" alt="T1-R1-S000-int-msg" src="https://github.com/user-attachments/assets/86839f6e-e80b-4c8f-bfde-cc84307e28f3" />

### 6️⃣ Exit

```bash
end
```


### 7️⃣ Verify the serial controller

```bash
show controllers s0/0/0
```

**Expected Output ✅:**

<img width="563" height="99" alt="T1-R1-show-controllers" src="https://github.com/user-attachments/assets/67aef9df-8202-45b0-b0ae-0a85e4d4b10d" />

Note: R1 is the DCE Data Communications Equipment


### ✅ Configure R2 (Serial + IP Address)

--- 

### 1️⃣ global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Enter the serial interface

```bash
interface s0/0/0
```

### 3️⃣ Try setting clock rate

```bash
clock rate 128000
```

**Expected Output ✅:**

<img width="445" height="45" alt="T1-R2-not-DCE" src="https://github.com/user-attachments/assets/3e15fcc2-206c-4632-98d2-46f47f287f03" />

Note R2 is DTE (Data Terminal Equipment) that is why I couldnt set the clock rate.

### 4️⃣ Configure the IP address

```bash
ip address 192.168.12.2 255.255.255.252
```

### 5️⃣ Enable the interface

```bash
no shutdown
```

### 6️⃣ Exit

```bash
end
```


### 7️⃣ Verify the serial controller

```bash
show controllers s0/0/0
```

**Expected Output ✅:**

<img width="578" height="101" alt="T1-R2-show-cont" src="https://github.com/user-attachments/assets/a13e3564-5967-462e-b251-6d894c45a422" />

---

## 🌐 Part B: Configure OSPF on R1 and R2 (Serial Link)

### ✅ Configure OSPF on R1

### 1️⃣ Enter global configuration mode

```bash
enable
configure ternimal
```

### 2️⃣ Enter OSPF process 1

```bash
router ospf 1
```

### 3️⃣ Enable OSPF on the serial network

```bash
network 192.168.12.0 0.0.0.3 area 0
```

### 4️⃣ Verify OSPF

```bash
do show ip protocols
```

**Expected Output ✅:**

<img width="653" height="267" alt="T1B-R1-verify-ospf" src="https://github.com/user-attachments/assets/67147b74-dad4-43a4-b60d-ec7553c2efa3" />

---

### ✅ Configure OSPF on R2

### 1️⃣ Enter global configuration mode

```bash
enable
configure ternimal
```

### 2️⃣ Enter OSPF process 1

```bash
router ospf 1
```

### 3️⃣ Enable OSPF on the serial network

```bash
network 192.168.12.0 0.0.0.3 area 0
```

### 4️⃣ Verify OSPF

```bash
do show ip protocols
```

**Expected Output ✅:**

<img width="669" height="336" alt="T1B-R2-verify-ospf" src="https://github.com/user-attachments/assets/17b73e2a-b31e-4030-b729-8330f0c3cc55" />

