# 📊 Task 1 – Configure SNMP Communities on R1

## 🎯 Goal
Configure **SNMP communities** on **R1** so it can be **monitored and managed remotely** using SNMP.

I will configure:
- 🔒 **Read-only community:** `Cisco1`
- ✏️ **Read/Write community:** `Cisco2`

📌 Community strings act like **passwords** for SNMP access.

## 🧠 Why This Matters
- **Read-only (RO)** allows monitoring (SNMP Get)
- **Read/Write (RW)** allows configuration changes (SNMP Set)
- SNMP is commonly used by **network monitoring tools** (SolarWinds, Nagios, etc.)

## Topology For Reference

<img width="333" height="135" alt="Topology" src="https://github.com/user-attachments/assets/cb46b216-b82f-4c84-8a90-aabeda8c2800" />

---

## 🗺️ SNMP Configuration Summary

| Community | Access Level | Purpose |
|---------|-------------|--------|
| `Cisco1` | Read-only | Monitoring (Get) |
| `Cisco2` | Read/Write | Management (Set) |

---

##  Configure R1

### 1️⃣ Enter Global Configuration Mode

#### ♦️ On R1:

```bash
enable
configure terminal
```

### 2️⃣ Configure Read-Only SNMP Community


```bash
snmp-server community Cisco1 ro
```

✅ This allows SNMP **Get** messages only.


### 3️⃣ Configure Read/Write SNMP Community

```bash
snmp-server community Cisco2 rw
```

⚠️ This allows SNMP **Set** messages (can change device settings).

---

### 4️⃣ Exit and Save the Configuration

```bash
end
write memory
```

---



