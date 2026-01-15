# 🛠️ Task 1 Configure IP Addressing  and Routing for Full Connectivity

## 📌 Objective

Configure **IP addressing** on all devices and configure **static routing** on the routers so the network has **full end-to-end connectivity**.

This step is required before attempting any **TFTP or FTP file transfers**.

---

## 🧠 Simple Explanation
- All devices must have correct **IP addresses**
- Routers must know how to reach **remote networks**
- File transfers (TFTP/FTP) will **fail** if connectivity is not working

## Topology For Reference

<img width="545" height="196" alt="topology" src="https://github.com/user-attachments/assets/1895f9fd-c6d2-42f5-ba47-2e54b059671f" />

---

## 🌐 Addressing Overview


| Device | Interface | IP Address | Subnet Mask |
|------|----------|------------|-------------|
| R1 | G0/1 | 10.0.0.254 | 255.255.255.0 |
| R1 | G0/0 | 192.168.12.1 | 255.255.255.252 |
| R2 | G0/0 | 192.168.12.2 | 255.255.255.252 |
| SRV1 | NIC | 10.0.0.1 | 255.255.255.0 |

---

# 🟢 Configure R1

## 1️⃣ Configure R1 Interfaces 

#### ♦️Enter Global Configuration Mode:

```bash
enable
configure terminal
```

#### ♦️ Configure R1 G0/0 interface

```bash
interface g0/0
 ip address 192.168.12.1 255.255.255.252
 no shutdown
```

#### ♦️ Configure R1 G0/1 interface

```bash
interface g0/1
 ip address 10.0.0.254 255.255.255.0
 no shutdown
```

## 2️⃣ Configure R1 Interfaces 


#### ♦️Enter Global Configuration Mode:

```bash
enable
configure terminal
```

#### ♦️ Configure R2 G0/0 interface

```bash
interface g0/0
 ip address 192.168.12.2 255.255.255.252
 no shutdown
```

## 3️⃣ Configure SRV1 IP Settings (Desktop GUI)

On SRV1:

- IP Address: `10.0.0.1`
- Subnet Mask: `255.255.255.0`
- Default Gateway: `10.0.0.254`

