# Configuring Standard ACL Lab 🚦📋

## 📌 Summary
In this lab I will configure **standard Access Control Lists (ACLs)** to control traffic flow between networks.  
You will first configure **OSPF** to ensure full connectivity, then apply **standard numbered ACLs on R1** and **standard named ACLs on R2** to enforce specific network security policies.



## Topology For Reference

<img width="734" height="267" alt="topology" src="https://github.com/user-attachments/assets/b86b0c9f-dbe1-49b2-8e7d-603331823c9c" />

### 🗂️ Tasks

### 🌐 Task 1: Configure OSPF for Full Connectivity
Configure **OSPF** on **R1** and **R2** to allow full connectivity between all PCs and servers before applying any ACLs.

### 🚫 Task 2: Configure Standard ACLs to Enforce Network Policies
Configure **standard numbered ACLs on R1** and **standard named ACLs on R2** to meet the following requirements:

#### 🅰️ Task 2A: Restrict Access to 192.168.1.0/24
Only **PC1** and **PC3** are allowed to access the **192.168.1.0/24** network.

#### 🅱️ Task 2B: Block 172.16.2.0/24 from 192.168.2.0/24
Hosts in the **172.16.2.0/24** network must not be able to access **192.168.2.0/24**.

#### 🅲 Task 2C: Block 172.16.1.0/24 from 172.16.2.0/24
Traffic from **172.16.1.0/24** must not be allowed to access **172.16.2.0/24**.

#### 🅳 Task 2D: Block 172.16.2.0/24 from 172.16.1.0/24
Traffic from **172.16.2.0/24** must not be allowed to access **172.16.1.0/24**.

---

## 📚 Navigation

| Section / File | Description |
|---------------|-------------|
| [**topology.png**](topology.png) | Network topology diagram for the Standard ACL lab |
| [**task-configs/**](task-configs) | Step-by-step configuration tasks (Task 1, Task 2A–2D) |
| [**pkt-files/**](pkt-files) | Packet Tracer files (blank & completed lab version) |
| [**reflection.md**](reflection.md) | Reflection and lessons learned |

---

## ✍️ Author Information

**Name:** *Daysean Mensah*  
**Course/Program:** *Cisco CCNA Studies*  
**Lab completion date:** December 19 2025.
