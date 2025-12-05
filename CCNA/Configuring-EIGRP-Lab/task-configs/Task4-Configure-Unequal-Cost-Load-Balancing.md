# ⚖️ Task 4: Configure Unequal-Cost Load Balancing on R1

## 🎯 Goal

In this task, I will configure **R1** to perform **unequal-cost load balancing** for traffic going to the **192.168.4.0/24** 
network behind R4.
EIGRP normally load-balances only over **equal-cost** paths. By using the **variance** command, I can also use
**feasible unequal-cost paths** and share the traffic over multiple links.

