# 🚫 Task 3 Disable CDP Globally on All Network Devices

## 📌 Objective
Disable **CDP globally** on every network device in the topology.

This stops the devices from sending and receiving CDP advertisements anywhere in the network.


# Topology For Reference

<img width="564" height="278" alt="topology" src="https://github.com/user-attachments/assets/cec8d912-5346-4e0a-a7d2-fc793f76f1c1" />

---


## 🛠️ Disable CDP on all network devices

Run this on **all network devices**:

## ⚙️ Configuration Steps (Run on Each Device)

#### 1️⃣ On each router and switch, Enter Global Config mode:

```bash
enable
configure terminal
```

#### 2️⃣ Disable CDP

```bash
no cdp run
end
```

## ✅ Verification

```bash
show cdp neighbors
```

<img width="639" height="81" alt="T3-cdp-disabled" src="https://github.com/user-attachments/assets/5382b67d-fe7f-4688-a00a-509be3bba8a1" />

