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

<img width="385" height="229" alt="T2-MIB-info" src="https://github.com/user-attachments/assets/885d26c7-2f65-4451-8b55-00d929009d37" />


**📌 If SNMP is set up correctly, R1 should respond to your Get requests.**

---

### 3️⃣ Use SNMP Get to Check R1 System Uptime
In the MIB Browser, request **sysUpTime**.

Under **SNMP MIBs** click MIB Tree all the way till you reach **.system**. See Below

<img width="530" height="411" alt="T2-1" src="https://github.com/user-attachments/assets/b72d4ca9-3b35-4f75-9482-709cdd536cfd" />

Then click Go. See bellow:

<img width="693" height="135" alt="T2-3" src="https://github.com/user-attachments/assets/bb00441f-7207-4f5e-8b22-d43c9ab4280e" />

**♦️ R1 has been up for about 10 hours**


