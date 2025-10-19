# VLSM-Subnetting Lab

This lab demonstrates subnetting using **Variable Length Subnet Masking (VLSM)** on the network `192.168.5.0/24`.  
The goal is to efficiently allocate IP address ranges for multiple LANs and a point-to-point connection while minimizing IP waste.

---

## Topology for reference
<img width="664" height="299" alt="topology" src="https://github.com/user-attachments/assets/3b11aff7-e314-474d-ab95-456735eacf7e" />


## 🧩 Objectives
- Subnet the `192.168.5.0/24` network using VLSM to meet host requirements for each LAN.
- Assign IP addresses to routers interfaces and PCs.
- Configure static routes on each router so all LANs can communicate.
- Verify end-to-end connectivity between all PCs.

---

## 🧠 Tasks
| Task | Description |
|------|--------------|
| **Task 1** | Subnet the `192.168.5.0/24` network for each LAN and point-to-point link. |
| **Task 2** | Assign the **last usable IP** of each subnet to the router interface. |
| **Task 3** | Assign the **first usable IP** of each subnet to the PC in that LAN. |
| **Task 4** | Configure static routes on R1 and R2 to enable full network connectivity. |

---

## 🌐 Subnet Allocation Table

| LAN              | Network Address | Subnet Mask         | First Usable IP  | Last Usable IP   | Default Gateway (Router IP) | Broadcast IP   |
|-------------------|----------------|---------------------|-----------------|-----------------|-----------------------------|----------------|
| **LAN2 (64 hosts)** | 192.168.5.0     | 255.255.255.128 (/25) | 192.168.5.1     | 192.168.5.126   | 192.168.5.126              | 192.168.5.127  |
| **LAN1 (45 hosts)** | 192.168.5.128   | 255.255.255.192 (/26) | 192.168.5.129   | 192.168.5.190   | 192.168.5.190              | 192.168.5.191  |
| **LAN3 (14 hosts)** | 192.168.5.192   | 255.255.255.224 (/27) | 192.168.5.193   | 192.168.5.222   | 192.168.5.222              | 192.168.5.223  |
| **LAN4 (9 hosts)**  | 192.168.5.224   | 255.255.255.240 (/28) | 192.168.5.225   | 192.168.5.238   | 192.168.5.238              | 192.168.5.239  |
| **Point-to-Point**  | 192.168.5.240   | 255.255.255.252 (/30) | 192.168.5.241   | 192.168.5.242   | R1: 192.168.5.241 / R2: 192.168.5.242 | 192.168.5.243  |

---

## ⚙️ Configuration Summary

- **Routers (R1 & R2):**
  - Configured LAN and point-to-point interfaces with appropriate subnet IPs.
  - Configured Static routes to reach all remote networks(other LANs).

- **PCs:**
  - Assigned first usable IP of their subnet.
  - Default gateway set to the router’s IP (last usable IP of the subnet).

---

## 🧪 Testing and Verification

- Verified connectivity between all LANs using `ping`.
- Fixed routing and IP misconfigurations to ensure successful communication across networks.
- Confirmed the static routing using Cisco Packet Tracer simulation mode.

---

## ✍️ Author Information

**Name:** *Daysean Mensah*  
**Course/Program:** *Cisco CCNA Studies*  
