# 🧩 Task 1 Subnet 192.168.5.1.0/24 Network 

This task focuses on subnetting the **192.168.5.0/24** network into smaller subnets for each LAN and a point-to-point link between routers.

---

## 🧠 Subnetting Notes

Understanding how subnet ranges are determined:

- 🧩 **First usable IP** = Network Address + 1  
- 📦 **Last usable IP** = Broadcast IP − 1  
- ➕ **Next Network Address** = Previous Broadcast IP + 1
- ✅ Notice everytime I calculate the number of usable host I subtract 2 (broadcast IP and Network Address)

---

## 🌐 LAN2 64 Hosts

| Detail | Value |
|--------|--------|
| **Subnet** | 192.168.5.0/25 |
| **Subnet Mask** | 255.255.255.128 |
| **Usable Hosts** | 2⁷ − 2 = 126 |
| **Network Address** | 192.168.5.0 |
| **Broadcast IP** | 192.168.5.127 |
| **First Usable IP** | 192.168.5.1 |
| **Last Usable IP** | 192.168.5.126 |
| **Broadcast (Binary)** | 11000000.10101000.00000101.01111111 |

📝 **Note:** LAN2 requires 64 hosts, and /25 provides 126 usable addresses, plenty of room for future growth.

---

## 🖥️ LAN1 45 Hosts

| Detail | Value |
|--------|--------|
| **Subnet** | 192.168.5.128/26 |
| **Subnet Mask** | 255.255.255.192 |
| **Usable Hosts** | 2⁶ − 2 = 62 |
| **Network Address** | 192.168.5.128 (LAN2 broadcast IP + 1)|
| **Broadcast IP** | 192.168.5.191 |
| **First Usable IP** | 192.168.5.129 |
| **Last Usable IP** | 192.168.5.190 |
| **Broadcast (Binary)** | 11000000.10101000.00000101.10111111 |

💡 **Note:** LAN1 starts right after LAN2’s broadcast address (`192.168.5.127 + 1`).

---

## 🖧 LAN3 14 Hosts

| Detail | Value |
|--------|--------|
| **Subnet** | 192.168.5.192/27 |
| **Subnet Mask** | 255.255.255.224 |
| **Usable Hosts** | 2⁵ − 2 = 30 |
| **Network Address** | 192.168.5.192 (LAN1 broadcast IP + 1)|
| **Broadcast IP** | 192.168.5.223 |
| **First Usable IP** | 192.168.5.193 |
| **Last Usable IP** | 192.168.5.222 |
| **Broadcast (Binary)** | 11000000.10101000.00000101.11011111 |

🧠 **Note:** Although /28 (14 usable) could work exactly, i used /27 was to allow for **future expansion**.

---

## 🏠 LAN4 9 Hosts

| Detail | Value |
|--------|--------|
| **Subnet** | 192.168.5.224/28 |
| **Subnet Mask** | 255.255.255.240 |
| **Usable Hosts** | 2⁴ − 2 = 14 |
| **Network Address** | 192.168.5.224 (LAN3 broadcast IP + 1)|
| **Broadcast IP** | 192.168.5.239 |
| **First Usable IP** | 192.168.5.225 |
| **Last Usable IP** | 192.168.5.238 |
| **Broadcast (Binary)** | 11000000.10101000.00000101.11101111 |

💡 **Note:** /28 perfectly supports up to 14 hosts which ideal for small networks like LAN4.

---

## 🔗 Point-to-Point Connection (R1 ↔ R2)

| Detail | Value |
|--------|--------|
| **Subnet** | 192.168.5.240/30 |
| **Subnet Mask** | 255.255.255.252 |
| **Usable Hosts** | 2² − 2 = 2 |
| **Network Address** | 192.168.5.240 (LAN4 broadcast IP + 1)|
| **Broadcast IP** | 192.168.5.243 |
| **First Usable IP** | 192.168.5.241 (R1) |
| **Last Usable IP** | 192.168.5.242 (R2) |
| **Broadcast (Binary)** | 11000000.10101000.00000101.11110011 |

🛰️ **Used for:** Direct router-to-router communication between **R1** and **R2**.

---

## ✅ Summary Table

| LAN | Subnet (Prefix) | Subnet Mask | Usable Hosts | Network Address | Broadcast | Gateway |
|------|----------------|--------------|---------------|----------------|------------|----------|
| LAN2 | 192.168.5.0/25 | 255.255.255.128 | 126 | 192.168.5.0 | 192.168.5.127 | 192.168.5.126 |
| LAN1 | 192.168.5.128/26 | 255.255.255.192 | 62 | 192.168.5.128 | 192.168.5.191 | 192.168.5.190 |
| LAN3 | 192.168.5.192/27 | 255.255.255.224 | 30 | 192.168.5.192 | 192.168.5.223 | 192.168.5.222 |
| LAN4 | 192.168.5.224/28 | 255.255.255.240 | 14 | 192.168.5.224 | 192.168.5.239 | 192.168.5.238 |
| P2P  | 192.168.5.240/30 | 255.255.255.252 | 2 | 192.168.5.240 | 192.168.5.243 | R1: .241 / R2: .242 |

---

📘 **Conclusion:**  
This subnet plan efficiently divides the **192.168.5.0/24** network to meet all host requirements while leaving room for scalability and router to router communication.
