# 🔎 Task 2 – Use SNMP Get Messages (MIB Browser on PC1)

## 🎯 Goal

Use **SNMP Get** messages from **PC1’s MIB Browser** to learn information about **R1**, including:
- ⏱️ System uptime (how long R1 has been running)
- 🏷️ Current hostname on R1
- 🔌 How many interfaces R1 has
- 📡 What those interfaces are
- ➕ Any other useful details you can discover with SNMP Get

---

## Topology For Reference

<img width="333" height="135" alt="Topology" src="https://github.com/user-attachments/assets/cb46b216-b82f-4c84-8a90-aabeda8c2800" />

## ✅ Step-by-Step (PC1)

### 1️⃣ Open the MIB Browser on PC1

- Click **PC1**
- Go to **Desktop**
- Open **MIB Browser** 


---

### 2️⃣ Configure the SNMP Target (R1)

In the MIB Browser settings:
- Set the **Target IP** to **R1’s IP address**
- Set the **Read Community** to: `Cisco1`
- Set the **Write Community** to: `Cisco2`
- Make sure the operation is **GET**

**📌 If SNMP is set up correctly, R1 should respond to your Get requests.**


---
