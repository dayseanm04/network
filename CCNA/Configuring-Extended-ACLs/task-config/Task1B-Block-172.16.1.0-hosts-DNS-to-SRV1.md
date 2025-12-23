# 🧩 Task 1B – Block DNS Access from 172.16.1.0/24 to SRV1

## 🎯 Goal

Configure an **extended ACL** on **R1** so that hosts in the **172.16.1.0/24** network **cannot access DNS services on SRV1**, while all other traffic remains permitted.

## Topology For Reference

<img width="730" height="251" alt="topology" src="https://github.com/user-attachments/assets/d75351f9-45c7-4d4c-b65a-e06aba9cedc8" />

---

--

## Configure R1

### 1️⃣ Enter Global Configuration Mode

```bash
enable
configure terminal
```

### 2️⃣ Configure the Extended named ACL

```bash
ip access-list extended block-172.16.1.0-hosts-DNS
deny udp 172.16.1.0 0.0.0.255 host 192.168.1.100 eq 53
deny tcp 172.16.1.0 0.0.0.255 host 192.168.1.100 eq 53
```

**Note📌:** Blocking both UDP and TCP ensures **all DNS access** is denied because DNS uses TCP and UDP port 53.


