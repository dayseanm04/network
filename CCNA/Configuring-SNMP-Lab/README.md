# 📊 Configuring SNMP Lab

## 📘 Lab Overview

In this lab, I will configure basic **Simple Network Management Protocol (SNMP)** test it using **Cisco Packet Tracer**. The lab shows how network devices can **monitor and manage remotely** using SNMP **Get** and **Set** messages.

I will configure SNMP communities on a router, use a **MIB browser** to retrieve device information, and modify router configuration using SNMP.

⚠️ *Note: SNMP functionality is limited in Packet Tracer.*

---

## 🧪 Lab Tasks

### 🧩 Task 1 – Configure SNMP Communities on R1
- Configure a **read-only** SNMP community
- Configure a **read/write** SNMP community
- These communities control what information can be read or modified via SNMP

📌 *Community strings act like passwords for SNMP access.*

---

### 🧩 Task 2 – Use SNMP Get Messages (Monitoring)
Using the **MIB Browser on PC1**, retrieve the following information from R1:

- ⏱️ System uptime (how long R1 has been running)
- 🏷️ Current hostname of R1
- 🔌 Number of interfaces on R1
- 📡 Names of those interfaces
- 🔎 Additional information such as:
  - Interface speed
  - MAC addresses
  - Routing information
  - Device software details

📌 *This task demonstrates how SNMP is used for monitoring.*

---

### 🧩 Task 3 – Use SNMP Set Message (Management)
- Use an **SNMP Set** message from PC1
- Change the **hostname of R1** remotely
- Verify the change from the router CLI

📌 *This demonstrates how SNMP can be used to manage and modify devices.*

---

## ✍️ Author Information

**Name:** *Daysean Mensah*  
**Course/Program:** *Cisco CCNA Studies*  
**Lab completion date:** December 31 2025.
