# Task1 Configure Serial Link and OSPF.md 🧵🌐


## 🎯 Goal
Configure the **serial connection between R1 and R2** (clock rate **128000**) and enable **OSPF** on the new serial link.

## Topology For Reference

<img width="707" height="307" alt="topololgy" src="https://github.com/user-attachments/assets/5f516c89-9322-44b4-8128-ff659905e275" />

## 🧵 Part A: Configure the Serial Link (R1 ↔ R2)

### ✅ Configure R1 (Serial + Clock Rate)

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


### 7️⃣ Verify the serial controller (confirm DCE on R1)

```bash
show controllers s0/0/0
```

**Expected Output ✅:**

<img width="563" height="99" alt="T1-R1-show-controllers" src="https://github.com/user-attachments/assets/67aef9df-8202-45b0-b0ae-0a85e4d4b10d" />





