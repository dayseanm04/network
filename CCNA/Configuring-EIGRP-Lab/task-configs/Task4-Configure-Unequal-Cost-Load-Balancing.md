# ⚖️ Task 4: Configure Unequal-Cost Load Balancing on R1

## Topology For reference

<img width="599" height="320" alt="topology" src="https://github.com/user-attachments/assets/e146f7b8-7977-42ce-8984-0c92d4d92d0d" />

## 🎯 Goal

In this task, I will configure **R1** to perform **unequal-cost load balancing** for traffic going to the **192.168.4.0/24** 
network behind R4.
EIGRP normally load-balances only over **equal-cost** paths. By using the **variance** command, I can also use
**feasible unequal-cost paths** and share the traffic over multiple links.


## 🔍 1️⃣ Verify Current Paths to 192.168.4.0/24

### 1️⃣ Enter privileged EXEC mode

```bash
enable
```

### 2️⃣ Check the current route to 192.168.4.0/24
```bash
show ip route eigrp
```

**Expected output ✅:**

<img width="956" height="325" alt="T4-R1-show-route" src="https://github.com/user-attachments/assets/17dfb1d6-a8c8-44d3-a298-0db375ae6706" />

- You should see one EIGRP route (D) to 192.168.4.0/24 using the best metric.
- Right now, R1 is not doing unequal-cost load balancing.

## ⚙️ 2️⃣ Configure Variance on R1


### 1️⃣ Enter global configuration mode

```bash
conf t
```

### 2️⃣ Enter router eigrp 100

```bash
router eigrp 100
```

### 3️⃣ Configure variance

```bash
variance 2
```

**Expected output ✅:**

<img width="955" height="137" alt="T4-R1-varriance-output" src="https://github.com/user-attachments/assets/b1fc908c-713a-4b63-9a4d-1d6f066e2137" />

<br/>

## 📊 Verify Unequal-Cost Load Balancing

```bash
show ip route eigrp
```

**Expected output ✅:**

<img width="793" height="252" alt="T4-show-eigrp-route-variance" src="https://github.com/user-attachments/assets/378433ac-af25-45fe-b7d5-00302a710f86" />

