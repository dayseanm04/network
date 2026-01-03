# 🌐 Task 2 - Telnet to R1 and Enable Syslog Messages on VTY (Terminal Monitor)

## 🎯 Goal
In this task, I will connect to **R1 using Telnet from PC1**, enable an unused interface to generate syslog messages, and learn why syslog messages **do not appear by default** on a Telnet/VTY session.

Then I will enable logging to the current VTY session using **`terminal monitor`** so syslog messages display in the Telnet window.

## Topology For Reference

<img width="568" height="245" alt="Topology" src="https://github.com/user-attachments/assets/2742761b-077b-4602-ac59-cc579decc1ba" />

---

## 🔐 Login Information (R1)
- Username: `jeremy`
- Password: `ccna`
- Enable password: `ccna`

---

### 1️⃣ Telnet from PC1 to R1 (G0/0 IP)

On **PC1**:
1. Click **Desktop**
2. Open **Command Prompt**
3. Telnet to R1’s G0/0 IP address:

```bash
telnet 192.168.1.1
```

Log in with:
- Username: jeremy
- Password: ccna

<img width="740" height="297" alt="T2-1" src="https://github.com/user-attachments/assets/f890cb80-4d2c-480c-aac5-7b7e4386db03" />


### 2️⃣ Enter Privileged EXEC Mode (R1)

```bash
enable
configure terminal
```

### 2️⃣ Enable the Unused Interface (G0/1)

```bash
interface g0/1
no shutdown
exit
```

<img width="748" height="238" alt="T2-P1-no-log" src="https://github.com/user-attachments/assets/34ce7a88-a472-4bd4-860d-cc0d13f42e0d" />

No syslog messages appear because when you connect via Telnet (VTY lines), syslog messages are not displayed to the terminal by default. 

### 3️⃣ Enable Syslog Messages to Display on the Current VTY Session

```bash
do terminal monitor
```

### 4️⃣ Test Syslog Display (Shutdown / No Shutdown G0/1)

Now generate syslog messages again by shutting down and re-enabling G0/1:

<img width="925" height="291" alt="PC1-log-display-telnet" src="https://github.com/user-attachments/assets/11a7ef60-6716-450b-a9e1-59019d2a4e50" />
