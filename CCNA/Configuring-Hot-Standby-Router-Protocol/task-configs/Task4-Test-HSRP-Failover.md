# Task4-Test-HSRP-Failover.md ⚠️🔁

## 🎯 Goal
Turn off **R1** (save the config first), then verify that **HSRP fails over** and **R2** is used as the default gateway when pinging **8.8.8.8** from **PC1**.

## Toplogy For Reference

<img width="624" height="284" alt="toplogy" src="https://github.com/user-attachments/assets/0f9e5564-4206-43af-a79f-1afe60dc7aa1" />

---

## 💾 Save Configuration on R1

### 1️⃣ On R1: Enter privileged EXEC mode

```bash
enable
```

### 2️⃣ Save the running configuration

```bash
write
```

### Power Off R1


- Click R1
- Go to Physical
- Toggle the power switch OFF


<img width="455" height="190" alt="T1-R4-off" src="https://github.com/user-attachments/assets/244df0dd-4c46-43de-9e33-08d484caf0e6" />

**Note:** R1 is off. ⏳ Wait a few seconds for HSRP to fail over.

