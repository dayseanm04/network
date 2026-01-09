# 🔐 Configure and Verify Switch Port Security

## 📌 Summary
This lab focuses on **securing switch interfaces using Port Security**.  

Port Security limits which **MAC addresses** are allowed on a switch port and defines what action the switch should take when a violation occurs.

In this lab, I configured different **port security policies** on two switches to compare how **shutdown** and **restrict** violation modes behave.  
Violations are intentionally triggered and observed to understand how switches respond in real network scenarios.

## Topology For Reference

<img width="589" height="226" alt="topology" src="https://github.com/user-attachments/assets/f75f290f-5b2f-41a0-9526-3651fbaddc79" />

---


## 🎯 Lab Objectives

By completing this lab, you will be able to:
- Configure **port security** on access and trunk interfaces
- Apply different **violation modes** (shutdown vs restrict)
- Control the **number of allowed MAC addresses**
- Use **sticky MAC learning**
- Observe and verify **port security violations**

---

## 🧪 Lab Tasks Overview

### 🛠️ Task 1 – Configure Port Security on Switch Interfaces

#### 🔹 Task 1A – SW1 Access Ports
Configure port security on the following **access interfaces**:

- **Switch:** SW1  
- **Interfaces:** F0/1, F0/2, F0/3  

**Port Security Policy:**

- 🚫 Violation Mode: **Shutdown**
- 🔢 Maximum MAC Addresses: **1**
- 📌 Sticky Learning: **Disabled**
- ⏱️ Aging Time: **1 hour**

📌 *Purpose:* Strictly secure access ports so any violation immediately disables the interface.

---

#### 🔹 Task 1B – SW2 Trunk Port
Configure port security on the following interface:

- **Switch:** SW2  
- **Interface:** G0/1  

**Port Security Policy:**
- ⚠️ Violation Mode: **Restrict**
- 🔢 Maximum MAC Addresses: **4**
- 📎 Sticky Learning: **Enabled**

📌 *Purpose:* Allow multiple MAC addresses while logging violations without shutting down the port.

---




