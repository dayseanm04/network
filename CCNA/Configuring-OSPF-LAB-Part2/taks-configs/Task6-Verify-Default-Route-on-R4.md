# 🧩 Task6 Verify Default Route on R4.md

## 🎯 Goal  
Verify whether **R4** has successfully learned the **default route (0.0.0.0/0)** that R1 is advertised into the OSPF domain.

---
## Topology For Reference

<img width="711" height="341" alt="Topology" src="https://github.com/user-attachments/assets/53e6080d-57be-4f5f-b410-c3046016c538" />

## 🛠️ Step-by-Step: Verify Default Route on R4

### 1️⃣ Enter privileged EXEC mode

```bash
enable
```

### 2️⃣ View the routing table

```bash
show ip route
```
