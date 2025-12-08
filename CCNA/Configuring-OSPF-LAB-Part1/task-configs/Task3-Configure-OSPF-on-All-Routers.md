# 🧩 Task 3 – Configure OSPF on All Routers

## 🎯 Goal

In this task, I will:

- Configure **OSPF process 1** on **R1, R2, R3, and R4**
- Enable OSPF on all **router-to-router links** and **loopback interfaces**
- **NOT** enable OSPF on **R1's Internet link (G3/0)**
- Configure **passive interfaces** on loopbacks (and LAN interfaces where needed)
- Verify that OSPF is running and forming neighbor relationships
 
## Topology For Reference

<img width="711" height="341" alt="Topology" src="https://github.com/user-attachments/assets/53e6080d-57be-4f5f-b410-c3046016c538" />

---

## 🖥️ R1 – Configure OSPF (No OSPF on Internet Link)

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Enter OSPF process 1

```bash
router ospf 1
```

### 3️⃣ Enable OSPF on the R1–R3 link (F1/0)

```bash
network 10.0.13.0 0.0.0.3 area 0
```


### 4️⃣ Enable OSPF on the R1–R2 link (G0/0)

```bash
network 10.0.12.0 0.0.0.3 area 0
```

### 5️⃣ Enable OSPF on R1 loopback interface

```bash
network 1.1.1.1 0.0.0.0 area 0
```

### 6️⃣ Configure the loopback as a passive interface

``` bash
passive-interface loopback 0
```

### 7️⃣ Verify OSPF on R1

```bash
do show ip protocols
```

**Expected Output✅:**

<img width="782" height="344" alt="T3-R1-show-ip-protocols" src="https://github.com/user-attachments/assets/171fba7a-54e7-4dd4-b37a-eed987a01efa" />


---

## 🖥️ R2 – Configure OSPF

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Enter OSPF process 1

```bash
router ospf 1
```

### 3️⃣ Enable OSPF on the R2–R4 link (F1/0)

```bash
network 10.0.24.0 0.0.0.3 area 0
```

### 4️⃣ Enable OSPF on the R2–R1 link (G0/0)

```bash
network 10.0.12.0 0.0.0.3 area 0
```

### 5️⃣ Enable OSPF on R2 loopback interface

```bash
network 2.2.2.2 0.0.0.0 area 0
```

### 6️⃣ Configure the loopback as a passive interface

``` bash
passive-interface loopback 0
```

### 7️⃣ Verify OSPF on R2

---

## 🖥️ R3 – Configure OSPF

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Enter OSPF process 1

```bash
router ospf 1
```

### 3️⃣ Enable OSPF on the R3–R1 link (F1/0)

```bash
network 10.0.13.0 0.0.0.3 area 0
```

### 4️⃣ Enable OSPF on the R3–R4 link (F2/0)

```bash
network 10.0.34.0 0.0.0.3 area 0
```

### 5️⃣ Enable OSPF on the R3 loopback interface

```bash
network 3.3.3.3 0.0.0.0 area 0
```

### 6️⃣ Configure the loopback as a passive interface

``` bash
passive-interface loopback 0
```

### 7️⃣ Verify OSPF on R3

---

## 🖥️ R4 – Configure OSPF

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Enter OSPF process 1

```bash
router ospf 1
```

### 3️⃣ Enable OSPF on the R4–R2 link (F1/0)

```bash
network 10.0.24.0 0.0.0.3 area 0
```

### 4️⃣ Enable OSPF on the R4–R3 link (F2/0)

```bash
network 10.0.34.0 0.0.0.3 area 0
```

### 5️⃣ Enable OSPF on the R3 loopback interface

```bash
network 4.4.4.4 0.0.0.0 area 0
```

### 6️⃣ Configure the loopback as a passive interface

``` bash
passive-interface loopback 0
```

### 7️⃣ Verify OSPF on R4

