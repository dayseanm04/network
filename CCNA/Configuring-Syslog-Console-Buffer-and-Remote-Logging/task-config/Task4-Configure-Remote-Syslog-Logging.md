# 🌍 Task 4 - Enable Remote Syslog Logging to SRV1 (Debugging Level)

## 🎯 Goal
In this task, I will configure **R1** to send syslog messages to the **Syslog Server (SRV1)** and set the logging level to **debugging**.  

This simulates a real enterprise setup where logs are centralized on a server for monitoring and troubleshooting. 

## Topology For Reference

<img width="568" height="245" alt="Topology" src="https://github.com/user-attachments/assets/2742761b-077b-4602-ac59-cc579decc1ba" />

---

## 🧩 Configure R1 or From PC1 or PC2

### 1️⃣ Enter Global Configuration Mode
On **R1**:

```bash
enable
configure terminal
```

### 2️⃣ Configure the Remote Syslog Server (SRV1)

```bash
logging host 192.168.1.100
```

### 3️⃣ Set the Syslog Trap Level to Debugging

```bash
logging trap debugging
```

**Expected Log ✅:**

<img width="956" height="114" alt="T4-syslog-server-log" src="https://github.com/user-attachments/assets/f072b152-e5a9-4623-80b0-c2996c51f83f" />

### 4️⃣ Verify Syslog Configuration on R1

```bash
do show logging
```

