# 🖥️ Task 1 - Initial SW2 Configuration via Console

## 🎯 Goal
SW2 is newly added and not configured yet. In this task, I will use **Laptop1 connected to SW2’s console port** to perform the basic setup:
- Hostname
- Enable secret
- Local username/password
- VLAN 1 SVI management IP
- Default gateway

## Reference Topology

<img width="545" height="224" alt="topology" src="https://github.com/user-attachments/assets/ae47e659-6807-4ae7-9c97-e89aa8e4ebba" />


---

## 🧩 Step-by-Step Config

### 1️⃣ Connect Laptop1 to SW2 Console

#### ♦️ On **Laptop1**:
- Click **Desktop**
- Click **Terminal**
- Keep the default terminal settings (9600 baud, 8 data bits, no parity, 1 stop bit, no flow control)

<img width="721" height="340" alt="Laptop1-terminak" src="https://github.com/user-attachments/assets/8b6a7037-ef87-4e44-8d59-e4d278cfa802" />

- Click **OK**

---

### 2️⃣ Enter Privileged EXEC Mode
```bash
enable
