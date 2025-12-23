# 🌐 Task 2 – Configure Static NAT on R1

## 🎯 Goal
Configure **Static NAT** on **R1** so that internal hosts (PC1, PC2, PC3) in the `172.16.0.0/24` LAN can access the internet by being mapped to public IPs in the `100.0.0.0/24` range.

## Topology For Reference

<img width="648" height="227" alt="Topology" src="https://github.com/user-attachments/assets/9eff3467-85fb-40f2-a50c-a3eca4d670d2" />

---

### 🔌 Interfaces (NAT Roles)
| R1 Interface | Connected To | NAT Role |
|------------|--------------|----------|
| `G0/1` | `172.16.0.0/24` LAN | **inside** |
| `G0/0` | Internet | **outside** |

### 🖥️ Static NAT Mappings
| Device | Inside Local (Private) | Inside Global (Public) |
|--------|-------------------------|------------------------|
| PC1 | `172.16.0.1` | `100.0.0.1` |
| PC2 | `172.16.0.2` | `100.0.0.2` |
| PC3 | `172.16.0.3` | `100.0.0.3` |

---

## Configure R1

### 1️⃣ Enter Global Configuration Mode

```bash
enable
configure terminal
```

### 2️⃣ Set the Inside Interface (LAN)

```bash
interface G0/1
ip nat inside
```


### 3️⃣  Set the Inside  Interface (Internet)
Go to the internet-facing interface and mark it as **NAT inside**:

```bash
interface g0/1
ip nat inside
```

**Note 📌 This tells R1 that traffic coming from this interface is from the **inside network**.**

---

### 4️⃣ Set the Outside Interface (Internet)

```bash
interface g0/0
ip nat outside
exit
```

**Note📌 This tells R1 that traffic leaving this interface is going to the outside (internet)**. 

---














