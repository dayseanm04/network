# 🛠️ Task 1 – Configure-R1-as-DHCP-Server

## 📌 Objective

Configure **R1** to act as a **DHCP server** for the LAN so that clients can automatically receive IP address information.

I will configure a **legitimate and trusted DHCP server**, which is required before enabling and testing **DHCP Snooping**.

## 🧠 Simple Explanation

- DHCP automatically assigns IP addresses to clients
- Some IP addresses should be **reserved** and not handed out
- The router will act as the **default gateway** for all DHCP clients

📌 This setup represents a common **small enterprise / campus DHCP design**.

## Topology For Reference

<img width="667" height="221" alt="topology" src="https://github.com/user-attachments/assets/0437e21d-9c1c-483d-b25a-dc0aa1e8f15a" />

---


## 🌐 DHCP Network Information

| Item | Value |
|-----|------|
| Network | 192.168.1.0 /24 |
| Default Gateway | 192.168.1.1 |
| Excluded Range | 192.168.1.1 – 192.168.1.9 |
| DHCP Server | R1 |

## ⚙️ Configuration Steps (R1)


### 1️⃣ Enter Global Configuration Mode

```bash
configure terminal
```

## 2️⃣ Exclude Reserved IP Addresses

```bash
ip dhcp excluded-address 192.168.1.1 192.168.1.9
```








