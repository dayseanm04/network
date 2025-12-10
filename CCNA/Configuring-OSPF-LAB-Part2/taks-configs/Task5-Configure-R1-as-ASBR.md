# Task5-Configure-R1-as-ASBR.md

## 🎯 Objective  
Configure **R1** as an Autonomous System Border Router (ASBR) that advertises a **default route** into the OSPF domain.


## Topology For Reference

<img width="711" height="341" alt="Topology" src="https://github.com/user-attachments/assets/53e6080d-57be-4f5f-b410-c3046016c538" />

---

## 🛠️ Step-by-Step: Configure Default Route on R1

### 1️⃣ **Enter privileged EXEC mode**

```bash
enable
```

### 2️⃣ View the current routing table (optional check)

```bash
show ip route
```

**Expected Ouput ✅:**

<img width="906" height="472" alt="T5-R1-show-route" src="https://github.com/user-attachments/assets/ac58aad8-acd8-476b-8f24-373088019fc6" />

**Note: There is no default route on R1.**

