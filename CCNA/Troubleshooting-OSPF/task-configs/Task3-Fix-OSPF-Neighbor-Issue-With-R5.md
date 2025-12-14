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

**Expected Output ✅:**

<img width="864" height="119" alt="T3-R2-show-ospf-neighbor" src="https://github.com/user-attachments/assets/aed325e7-4fdc-4a67-82f0-871ae782fa14" />
