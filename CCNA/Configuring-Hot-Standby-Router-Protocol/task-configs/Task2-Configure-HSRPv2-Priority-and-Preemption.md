# Task2 Configure HSRPv2 Priority and Preemption.md 🔁⚙️

## 🎯 Goal
Configure **HSRPv2** on **R1** and **R2**.  
- Raise **R1** priority above the default  
- Lower **R2** priority below the default  
- Enable **preemption** 

## Toplogy For Reference

<img width="624" height="284" alt="toplogy" src="https://github.com/user-attachments/assets/0f9e5564-4206-43af-a79f-1afe60dc7aa1" />

---

## 🛠️ Configure HSRPv2 on R1

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Enter the interface config mode for the interface toward the PCs

```bash
interface g0/0
```

### 3️⃣ Enable HSRP version 2

```bash
standby version 2
```

### 4️⃣ Configure HSRP group 1 virtual IP (VIP)

```bash
standby 1 ip 10.0.1.254
```

**Expected Output ✅:**

<img width="786" height="167" alt="T1-R1-log" src="https://github.com/user-attachments/assets/44f8d8d6-f84a-42cb-a9b9-6cea37f04251" />


### 5️⃣ Raise R1 priority above the default

```bash
standby 1 priority 220
```

### 6️⃣ Enable preemption

```bash
standby 1 preempt
exit
```

### 7️⃣ Verify HSRP status on R1

```bash
show standby
```

**Expected Output ✅:**

<img width="727" height="257" alt="T2-R1-show-standby" src="https://github.com/user-attachments/assets/847de156-76bd-4285-a571-34f266be5a5d" />








