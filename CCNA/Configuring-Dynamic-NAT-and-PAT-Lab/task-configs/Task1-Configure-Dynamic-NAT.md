# 🌐 Task 1 – Configure Dynamic NAT on R1

## 🎯 Goal
Configure **Dynamic NAT** on **R1** so that hosts in `172.16.0.0/24` can access the internet using a **public IP pool** from `100.0.0.1` to `100.0.0.2` (subnet `100.0.0.0/24`).

## Topology For Reference

<img width="588" height="215" alt="Topology" src="https://github.com/user-attachments/assets/a0ad75ab-6982-416a-8c01-5fd83306f1b0" />

---

## ✅Configure R1

### 1️⃣ Enter Global Configuration Mode

```bash
enable
configure terminal
```


### 2️⃣ Configure the NAT Outside Interface (Internet Side)

```bash
interface g0/0
ip nat outside
```

**📌Note:  This tells R1 that traffic leaving this interface is going to the internet.**

### 3️⃣ Configure the NAT Inside Interface (LAN Side)

```bash
interface g0/1
ip nat inside
```
