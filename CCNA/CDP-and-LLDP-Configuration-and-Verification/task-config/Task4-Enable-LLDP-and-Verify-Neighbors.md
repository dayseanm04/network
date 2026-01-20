# 📡 Task 4 Enable LLDP and Verify Neighbors

## 📌 Objective
Enable **LLDP** on all network devices and verify neighbor discovery using LLDP.

In this lab:
- I will enable LLDP **globally** on every network device
- I will configfure LLDP **Tx/Rx** on the interfaces connected to other network devices

# Topology For Reference

<img width="564" height="278" alt="topology" src="https://github.com/user-attachments/assets/cec8d912-5346-4e0a-a7d2-fc793f76f1c1" />

---

# ⚙️ Part A — Enable LLDP Globally (All Devices)

### 🔷 On each router and switch:

#### 🟢 Enter Global Config mode:

```bash
enable
configure terminal
```

#### Enable LLDP Globally

```bash
lldp run
end
```











