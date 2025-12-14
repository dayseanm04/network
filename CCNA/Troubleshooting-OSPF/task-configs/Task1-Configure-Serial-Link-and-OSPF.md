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


