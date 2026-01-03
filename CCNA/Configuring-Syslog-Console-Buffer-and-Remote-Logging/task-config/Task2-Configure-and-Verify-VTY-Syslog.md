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


