# Task3 Fix OSPF Neighbor Issue With R5.md 🔄🤝

## 🎯 Goal
R2 and R4 will not become OSPF neighbors with **R5**.  
Troubleshoot why the adjacency is failing and fix the issue so R5 forms neighbors successfully.

## Topology For Reference

<img width="707" height="307" alt="topololgy" src="https://github.com/user-attachments/assets/5f516c89-9322-44b4-8128-ff659905e275" />

---

## 🧪 Step-by-Step: Confirm the Neighbor Problem

### 1️⃣ On R2: Check OSPF neighbors

```bash
enable
show ip ospf neighbor
```
