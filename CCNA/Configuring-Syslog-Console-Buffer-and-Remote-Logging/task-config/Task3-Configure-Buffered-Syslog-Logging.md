# 🧠 Task 3 — Enable Buffered Logging (8192 Bytes)

## 🎯 Goal
In this task, I will configure **R1** to store syslog messages in the **logging buffer** and set the buffer size to **8192 bytes**.  

Buffered logging is useful because it keeps log messages locally on the router so you can review them later (even if you didn’t see them live on the console or VTY).

## Topology For Reference

<img width="568" height="245" alt="Topology" src="https://github.com/user-attachments/assets/2742761b-077b-4602-ac59-cc579decc1ba" />

---


## 🧩 Configure R1

### 1️⃣ Enter Global Configuration Mode

```bash
enanle
configure terminal
```

### 2️⃣ Enable Buffered Logging + Set Buffer Size (8192 Bytes)

```bash
logging buffered 8192
```

### 3️⃣ Verify Buffered Logs

```
do show logging
```

<img width="781" height="388" alt="T3-shbow-logging" src="https://github.com/user-attachments/assets/73344c99-f988-498e-8c26-857ee0a58cab" />

buffered logging is set to debugging
