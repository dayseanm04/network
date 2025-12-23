# 🧩 Task 1B – Block DNS Access from 172.16.1.0/24 to SRV1

## 🎯 Goal

Configure an **extended ACL** on **R1** so that hosts in the **172.16.1.0/24** network **cannot access DNS services on SRV1**, while all other traffic remains permitted.

## Topology For Reference

<img width="730" height="251" alt="topology" src="https://github.com/user-attachments/assets/d75351f9-45c7-4d4c-b65a-e06aba9cedc8" />

---


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

### 3️⃣ Permit all other traffic:

```bash
permit ip any any
```

### 4️⃣ Apply the ACL to R1 g0/0 inbound (toward 172.16.1.0/24)

```bash
interface g0/0
ip access-group block-172.16.1.0-hosts-DNS in
```

**Note:** ⚠️ This is required because ACLs have an **implicit deny** at the end.


### 5️⃣ Save Configuration 

```bash
end
write memory
```

## 🧪Test the Policy

### ✅ Run a DNS Lookup from PC1

`nslookup index.html`

<img width="745" height="367" alt="T1B-PC1-nslookup" src="https://github.com/user-attachments/assets/ab149797-a855-41b2-8198-442eed63cc57" />

❌ DNS request **fails / times out** (DNS blocked)


### On R1 show access-lists

<img width="821" height="154" alt="T1B-R1-al" src="https://github.com/user-attachments/assets/89aa479f-cc0a-4b2b-8ad1-6b66439e418f" />

The ACL succesfully blocked the DNS requests

