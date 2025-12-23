# 🔐 Configuring Extended ACLs Lab

## 📘 Lab Overview
In this lab, I configured extended Access Control Lists (ACLs) to enforce **specific security policies** between internal networks and servers.  
Extended ACLs are used because they allow filtering based on **source IP, destination IP, protocol, and service ports**, providing more precise traffic control than standard ACLs.

This lab focuses on applying ACLs **close to the source** and verifying that only the intended traffic is blocked while all other traffic is permitted.


## Topology For Reference

<img width="730" height="251" alt="topology" src="https://github.com/user-attachments/assets/1de1fb1f-1bd4-4bb2-9e88-4bd4ed60396a" />

## 🎯 Lab Objectives
By completing this lab, you will be able to:

- ✅ Create **named extended ACLs**
- ✅ Block traffic based on **network, host, and service**
- ✅ Apply ACLs to the correct router interfaces
- ✅ Verify ACL behavior using testing and show commands



## 🧪 Lab Tasks

### 🧩 Task 1 – Configure Extended ACLs
Extended ACLs are created to enforce the following network policies:

#### 🔹 Task 1A – Block Network-to-Host Communication
- 🚫 Hosts in `172.16.2.0/24` **cannot communicate with PC1**
- 🎯 PC1 IP Address: `172.16.1.1`

#### 🔹 Task 1B – Block DNS Access
- 🚫 Hosts in `172.16.1.0/24` **cannot access DNS services** on SRV1
- 🎯 Service Blocked: **DNS (TCP & UDP port 53)**

#### 🔹 Task 1C – Block Web Services
- 🚫 Hosts in `172.16.2.0/24` **cannot access HTTP or HTTPS services** on SRV2
- 🎯 Services Blocked:
  - HTTP (port 80)
  - HTTPS (port 443)

## 🧭 Lab Navigation

| Section | Description |
|------|-------------|
| 📂 **pkt-files/** | Cisco Packet Tracer files (blank and completed versions of the lab) |
| 📂 **task-config/** | Step-by-step configuration tasks for each extended ACL |
| 📝 **reflection.md** | Summary of the lab and lessons learned |


---

## ✍️ Author Information

**Name:** *Daysean Mensah*  
**Course/Program:** *Cisco CCNA Studies*  
**Lab completion date:** December 21 2025.
