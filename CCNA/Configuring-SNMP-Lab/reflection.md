# 📝 Reflection – Configuring SNMP Lab

## 📘 Lab Summary
- In this lab, I configured **Simple Network Management Protocol (SNMP)** on a router and used a **MIB Browser** to monitor and manage the device remotely.
- I created both **read-only** and **read/write** SNMP communities on **R1**.
- Using **SNMP Get** messages, I gathered important information about the router.
- Using an **SNMP Set** message, I remotely changed the hostname of R1.
- This lab showed how SNMP is used for both **monitoring** and **management**.

---

## Topology For Reference

<img width="333" height="135" alt="Topology" src="https://github.com/user-attachments/assets/cb46b216-b82f-4c84-8a90-aabeda8c2800" />

## 🧠 What I Learned
- **SNMP uses a manager–agent model**:
  - The router (R1) acts as the **SNMP agent**
  - PC1 acts as the **SNMP manager**
- **Read-only communities** allow monitoring but prevent changes.
- **Read/write communities** allow configuration changes.
- SNMP Get messages can retrieve:
  - System uptime
  - Hostname
  - Interface count
  - Interface names
  - Other device details stored in the MIB
- SNMP Set messages can **modify device configuration remotely**, such as changing the hostname.

---


