# 🛰️ CDP and LLDP Configuration and Verification LAB

## 📌 Summary
This lab focuses on **network device discovery** using **CDP** and **LLDP**. I will use CDP to identify neighboring devices and fill in missing topology details (IP addresses and interface IDs). Then I will harden the network by disabling CDP where appropriate and enabling LLDP for standardized device discovery.

## 🎯 Lab Objectives

By completing this lab, you will be able to:
- Use **CDP** to discover neighbors and document missing topology details
- Disable CDP on **access ports connected to PCs**
- Disable CDP **globally** on network devices
- Enable **LLDP** globally and enable **Tx/Rx** on the interfaces connected to other network device
- Verify LLDP neighbor relationships

## Topology For Reference

<img width="564" height="278" alt="topology" src="https://github.com/user-attachments/assets/cec8d912-5346-4e0a-a7d2-fc793f76f1c1" />

---

## 🧪 Lab Tasks Overview

### 🔍 Task 1 – Discover and Document Topology Using CDP
- Use CDP and show commands to identify:
  - Missing **IP addresses**
  - Missing **interface IDs**
- Commands used include:
  - `show cdp neighbors`
  - `show ip interface brief`
  - PC IP configuration checks (ipconfig /all)

---

### 📴 Task 2 – Disable CDP on PC Facing Switch Ports
- Disable CDP on switch access ports connected to PCs

---


