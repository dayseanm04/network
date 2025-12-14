# Task2 Troubleshoot OSPF Missing-Route 🔍🧭

## 🎯 Goal
Only **R3** has a route to **10.0.2.0/24**.  
Find out **why other routers don’t learn it through OSPF**, then fix the issue so the route propagates across the OSPF domain.

## Topology For Reference

<img width="707" height="307" alt="topololgy" src="https://github.com/user-attachments/assets/5f516c89-9322-44b4-8128-ff659905e275" />


---

## 🧪 Step-by-Step: Confirm the Problem

### 1️⃣ On R3: Check the routing table

```bash
enable
show ip route
```

**Expected Output ✅:**

<img width="832" height="324" alt="T2-R3-route" src="https://github.com/user-attachments/assets/57deb459-c951-4f10-817a-109b550ae482" />

**Note:** R3 has the route to 10.0.2.0/24 network because its directly connected on its G0/0 interface

## 2️⃣ Check R4 routing table

```bash
enable
show ip route
```

**Expected Output ✅:**

<img width="832" height="362" alt="T2-R4-show-ip-route1" src="https://github.com/user-attachments/assets/99653abb-a16e-42bd-b85a-b024611eb9dc" />


