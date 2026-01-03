# 🖥️ Task 1 - Configure Console Syslog, Severity Levels, and Timestamps

## 🎯 Goal
In this task, I will connect to **R1 via the console**, generate **syslog messages** by shutting down and re-enabling an interface, identify the **severity level** of those messages, and enable **timestamps** for logging.

This task demonstrates how **console logging works by default** on Cisco routers and how syslog messages are generated during interface state changes.

## Topology For Reference

<img width="568" height="245" alt="Topology" src="https://github.com/user-attachments/assets/2742761b-077b-4602-ac59-cc579decc1ba" />

---

## 🔐 Login Information (R1)
- Username: `jeremy`
- Password: `ccna`
- Enable password: `ccna`

---

## 🧩 Step-by-Step Instructions

### 1️⃣ Connect to R1 via Console (PC2)
On **PC2**:
- Open **Desktop**
- Click **Terminal**

<img width="736" height="342" alt="PC2-Terminal" src="https://github.com/user-attachments/assets/8b11db92-64dc-4ffe-8afd-21454cd94d5c" />

- Cick OK
- Log in using the provided credentials

---

### 2️⃣ Enter Privileged EXEC Mode (R1)

#### ♦️ On PC2 Enter Global Configuration Mode

```bash
enable
configure terminal
```

### 3️⃣ Shut Down Interface G0/0

```bash
interface g0/0
shutdown
```

### 4️⃣ Re-Enable Interface G0/0

```bash
no shutdown
exit
```

<img width="923" height="263" alt="T1-R1-logs" src="https://github.com/user-attachments/assets/96766fd4-bd21-41b0-a0af-e577ae259647" />

Note there is no timestamp for the logs displayed. the interface messages generate severity level 5 (Notice) logs.



