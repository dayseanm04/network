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

### 2️⃣ Enter Global Configuration Mode

```bash
enable
configure terminal
```

### 3️⃣ Set the Hostname

```bash
hostname SW2
```

### 4️⃣ Configure the Enable Secret

```bash
enable secret ccna
```

### 5️⃣ Create a Local User Account

```bash
username jeremy secret ccna
```

### 6️⃣ Configure the VLAN 1 SVI (Management IP)

```bash
interface vlan 1
ip address 192.168.2.253 255.255.255.0
no shutdown
exit
```

### 7️⃣ Configure the Default Gateway

```bash
ip default-gateway 192.168.2.254
```

### 8️⃣ Save Config

```bash
end
write
```

## Verification

#### 🔶 show run | include secrete

<img width="583" height="97" alt="verifiy-user-secret" src="https://github.com/user-attachments/assets/6707ebff-56fe-438b-9177-3afa16f7cad8" />

#### 🔶 show run | include 192

<img width="551" height="80" alt="verifiy-ip" src="https://github.com/user-attachments/assets/9523209a-d1f8-4f5d-aaaf-ea9eb17d93a2" />

#### 🔶 show run | section Vlan

<img width="477" height="84" alt="verifiy-svi" src="https://github.com/user-attachments/assets/5316b630-38af-4416-98b5-25aab609d50f" />
