# 🧩 Task 1C – Block HTTP/HTTPS Access from 172.16.2.0/24 to SRV2

## 🎯 Goal
Configure an **extended ACL** on **R1** so that hosts in **172.16.2.0/24** **cannot access HTTP or HTTPS services on SRV2**, while all other traffic is allowed.

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
ip access-list extended block-172.16.2.0-hosts-HTTP
deny tcp 172.16.2.0 0.0.0.255 host 192.168.2.100 eq 80
deny tcp 172.16.2.0 0.0.0.255 host 192.168.2.100 eq 443
```

**Note📌:** This blocks traffic over HTTP and HTTPS.

### 3️⃣ Permit all other traffic:

```bash
permit ip any any
```

### 4️⃣ Apply the ACL to R1 g0/1 inbound (toward 172.16.2.0/24)

```bash
interface g0/1
ip access-group block-172.16.1.0-hosts-DNS in
```

**Note:** ⚠️ This is required because ACLs have an **implicit deny** at the end.


### 5️⃣ Save Configuration 

```bash
end
write memory
```

## 🧪Test the Policy
