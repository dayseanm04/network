# Task4-Test-HSRP-Failover.md ⚠️🔁

## 🎯 Goal
Turn off **R1** (save the config first), then verify that **HSRP fails over** and **R2** is used as the default gateway when pinging **8.8.8.8** from **PC1**.

## Toplogy For Reference

<img width="624" height="284" alt="toplogy" src="https://github.com/user-attachments/assets/0f9e5564-4206-43af-a79f-1afe60dc7aa1" />

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


<img width="455" height="190" alt="T4-R1-off" src="https://github.com/user-attachments/assets/244df0dd-4c46-43de-9e33-08d484caf0e6" />

**Note:** R1 is off. ⏳ Wait a few seconds for HSRP to fail over.

---

## Test Connectivity from PC1

### 1️⃣ On PC1: Ping the external server

- PC1 ➜ Desktop ➜ Command Prompt

```bash
ping 8.8.8.8
```

**Expected Ouput✅:**

<img width="746" height="393" alt="T4-PC1-Ping" src="https://github.com/user-attachments/assets/19a7c79d-76d0-4e65-a9ce-b20c46998cfc" />

### 2️⃣ Run traceroute to confirm the gateway path

```bash
tracert 8.8.8.8
```

**Expected Ouput✅:**

<img width="745" height="274" alt="T4-PC1-tracert" src="https://github.com/user-attachments/assets/114d7036-62e7-414e-a884-1089ab4ffea3" />







