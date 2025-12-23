# 🧩 Task 1A – Block 172.16.2.0/24 Hosts from PC1

## 🎯 Task Objective
Configure an **extended ACL** that prevents all hosts in the `172.16.2.0/24` network from communicating with **PC1**, while allowing all other traffic.

## Topology For Reference

<img width="730" height="251" alt="topology" src="https://github.com/user-attachments/assets/d75351f9-45c7-4d4c-b65a-e06aba9cedc8" />

---

## 🖥️ Network Details
| Device | IP Address | Network |
|------|-----------|--------|
| PC1 | `172.16.1.1/24` | 172.16.1.0/24 |
| PC3 | `172.16.2.1/24` | 172.16.2.0/24 |
| PC4 | `172.16.2.2/24` | 172.16.2.0/24 |

---

## Configure R1

### 1️⃣ Enter Global Configuration Mode

```bash
enable
configure terminal
```

### 2️⃣ Configure the Extended named ACL

```bash
ip access-list extended block-172.16.2.0-hosts-to-PC1
deny ip 172.16.2.0 0.0.0.255 host 172.16.1.1
```

### 3️⃣ Permit all other traffic:

```bash
permit ip any any
```


### 4️⃣ Apply the ACL to R1 g0/1 inbound (toward 172.16.2.0/24)

```bash
interface g0/
ip access-group block-172.16.2.0-hosts-to-PC1 in
```

### 5️⃣ Save Configuration 

```bash
end
write memory
```


## 🧪Test the Policy

#### ✅ Ping PC1 from PC3

**Expected Output✅:**

<img width="744" height="338" alt="T1A-PC3-PC1" src="https://github.com/user-attachments/assets/e0e0ffaf-b8ab-464b-bf04-555a624f17e8" />

### On R1 show access-lists

<img width="715" height="84" alt="T1A-R1-al" src="https://github.com/user-attachments/assets/c2e49311-9063-4d79-acf6-12fba51c6ce5" />

The ACL succesfully blocked the pings to PC1
