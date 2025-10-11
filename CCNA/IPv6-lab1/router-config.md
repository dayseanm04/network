# Router Configuration IPv6 (Tasks 1 & 2)

### Purpose
Step-by-step router configuration for enabling IPv6 and assigning IPv6 addresses on R1 to create a dual-stack (IPv4/IPv6) network. This covers **Task 1 (enable IPv6 routing)**, **Task 2 (assign IPv6 addresses to router interfaces)**.

## Topology for reference
<img width="437" height="334" alt="topology" src="https://github.com/user-attachments/assets/375fad54-2066-4fd5-aabe-d542a4d330a0" />

## Task 1: Enable IPv6 routing (R1)
**Goal:** enable IPv6 routing on the router to allow IPv6 routing

### 1️⃣ Enter global config mode
```bash
enable
configure terminal
```

### 2️⃣ enable IPv6 routing on R1
```bash
ipv6 unicast-routing
```

## Task 2: Configure IPv6 addresses on R1 interfaces
**Goal:** Assign the IPv6 gateway addresses for each connected network.

### 3️⃣ Steps (repeat for each interface):
- Enter interface configuration mode for each interface (G0/0, G0/1, G0/2).
- Assign the IPv6 address with a /64 prefix.
- Ensure the interface is not administratively down.

### 3️⃣ configure R1 g0/0 interface
```bash
int g0/0
 ipv6 addr 2001:DB8:0:1::1/64
 no shutdown
 exit
```

### 3️⃣ configure R1 g0/1 interface

```bash
int g0/1
 ipv6 add 2001:DB8:0:2::1/64
 no shutdown
 exit
```

### 3️⃣ configure R1 g0/2 interface

```bash
int g0/2
 ipv6 addr 2001:DB8:0:3::1/64
 no shutdown
 exit
```

## Note: I used the shortcut version of the commands(saves you time and less typing)
- int g0/1 is the shortcut version of the full command interface GigabitEthernet0/1
- ipv6 addr 2001::1/64 is the shortcut version of the full command ipv6 address ...

## Task 3: Verify IPv6 configuration on R1
**Goal:** Verify that IPv6 routing is enabled and that each interface has the correct IPv6 address.

```bash
show ipv6 int brief
```

**do show ipv6 int brief on R1:**
<img width="643" height="236" alt="show-ipv6-int" src="https://github.com/user-attachments/assets/438bef22-8afa-4157-8f5e-455ebe3452fb" />

## Expected results
- GigabitEthernet0/0 — 2001:DB8:0:1::1/64
- GigabitEthernet0/1 — 2001:DB8:0:2::1/64
- GigabitEthernet0/2 — 2001:DB8:0:3::1/64

