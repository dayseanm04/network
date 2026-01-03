# 📟 Configuring Syslog - Console, Buffer, and Remote Logging Lab

## 📌 Lab Overview
In this lab, I configured **Syslog logging** on a Cisco router to observe how system messages are generated, categorized, and delivered to different logging destinations.  
The lab focuses on **console logging**, **VTY logging**, **buffered logging**, and **remote syslog server logging**, which are essential for **monitoring, troubleshooting, and auditing network devices**.

This lab demonstrates how syslog messages behave differently depending on the connection method and logging configuration.

---

**Login Credentials (R1):**
- Username: `jeremy`
- Password: `ccna`
- Enable Password: `ccna`

---

## 📋 Lab Tasks

### 🖥️ Task 1 - Console Logging & Severity Levels
- Connect to **R1’s console port** using **PC2**
- Shut down and re-enable **G0/0**
- Observe generated **syslog messages**
- Identify the **severity level**
- Enable **timestamps** for logging messages

---

### 🌐 Task 2 - VTY Logging Behavior
- Telnet from **PC1** to **R1’s G0/0 interface**
- Enable the unused **G0/1 interface**
- Observe why **no syslog message appears**
- Enable logging to the **VTY lines** for the active session

⚠️ *Packet Tracer note:*  
> The `logging monitor` command is not available, but VTY logging is enabled by default.

---

### 🧠 Task 3 - Buffered Logging
- Enable **logging to the buffer**
- Configure the buffer size to **8192 bytes**

---

### 🌍 Task 4 - Remote Syslog Server Logging
- Configure **R1** to send logs to **SRV1**
- Set the logging level to **debugging**
- Verify logs are successfully received by the syslog server

---








