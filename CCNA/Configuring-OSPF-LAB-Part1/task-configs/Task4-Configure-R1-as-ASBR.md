# 🌐 Task 4 – Configure R1 as an ASBR

## 🎯 Goal

In this task, I will configure **R1** as an **ASBR (Autonomous System Border Router)**.  
R1 will:
- Have a **default static route** pointing to the ISP.
- **Advertise** that default route into the **OSPF domain** so that R2, R3, and R4 can use it as their path to the Internet.

## Topology For Reference

<img width="711" height="341" alt="Topology" src="https://github.com/user-attachments/assets/53e6080d-57be-4f5f-b410-c3046016c538" />

## 🔍 1️⃣ Check R1 routing table

### 1️⃣ Enter privileged EXEC mode

```bash
enable
```

### 2️⃣ View R1 routing table

```bash
show ip route
```

**Expected Ouput ✅:**

**Note: theres no defaault Route on R1**

