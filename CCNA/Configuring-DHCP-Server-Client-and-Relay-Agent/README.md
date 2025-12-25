# 📡 Configuring DHCP Server, Client, and Relay Agent Lab

## 📘 Lab Overview
In this lab, I will configure **Dynamic Host Configuration Protocol (DHCP)**. The lab demonstrates how a router can function as a **DHCP server**, a **DHCP client**, and how a **DHCP relay agent** is used to forward DHCP requests across different subnets.

This setup reflects real-world enterprise networks where centralized DHCP servers provide IP addresses to multiple remote networks.

## Topology For Reference

<img width="645" height="285" alt="Topology" src="https://github.com/user-attachments/assets/21f639d4-6d6f-4952-9de3-d255df077e99" />

---

## 🎯 Lab Objectives
By completing this lab, you will be able to:

- ✅ Configure multiple **DHCP pools** on a router
- ✅ Exclude reserved IP addresses from DHCP assignment
- ✅ Configure a router interface as a **DHCP client** and a **DHCP Server**
- ✅ Configure a router as a **DHCP relay agent**
- ✅ Verify DHCP address assignment from end devices

---

## 🧪 Lab Tasks

### 🧩 Task 1 – Configure DHCP Pools on R2
Configure the following DHCP pools:

### 🔹 POOL1 – **192.168.1.0/24**
- Reserve IPs: **.1** to **.10**
- DNS Server: **8.8.8.8**
- Domain Name: **jeremysitlab.com**
- Default Gateway: **R1**

### 🔹 POOL2 – **192.168.2.0/24**
- Reserve IPs: **.1** to **.10**
- DNS Server: **8.8.8.8**
- Domain Name: **jeremysitlab.com**
- Default Gateway: **R2**

### 🔹 POOL3 – **203.0.113.0/30**
- Reserve IP: **.1**
- Used for R1 R2 point to point

---



