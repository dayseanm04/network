# Task5-Examine-OSPF-LSDB.md 📚🧭


### 🎯 Goal
Examine the **OSPF Link-State Database (LSDB)** and identify which **LSAs** are present in the network.

## Topology For Reference

<img width="707" height="307" alt="topololgy" src="https://github.com/user-attachments/assets/5f516c89-9322-44b4-8128-ff659905e275" />

---

### 1️⃣ On R1 (or any router):

### 🔷 Enter privileged EXEC mode:

```bash
enable
```

### 🔷 2️⃣ View the OSPF database

```bash
show ip ospf database
```

**Expected Output✅:**

<img width="758" height="370" alt="T5-R1-ospf-db" src="https://github.com/user-attachments/assets/9da7918a-8578-4c79-8120-5bcee2c27dfe" />
