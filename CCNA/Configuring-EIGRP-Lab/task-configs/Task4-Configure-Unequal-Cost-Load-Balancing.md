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

