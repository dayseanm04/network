# 🌍 Configuring Dynamic NAT and PAT Lab

## 📘 Lab Overview
In this lab, I will configure **Dynamic NAT** and **Port Address Translation (PAT)** to allow multiple internal hosts to access the internet. The lab demonstrates the limitations of Dynamic NAT when the public IP pool is exhausted and how **PAT solves this problem by allowing many devices to share a single public IP address**.

## Topology For Reference

<img width="588" height="215" alt="Topology" src="https://github.com/user-attachments/assets/a0ad75ab-6982-416a-8c01-5fd83306f1b0" />

---

## 🎯 Lab Objectives
By completing this lab, you will be able to:

- ✅ Configure **Dynamic NAT** using a public IP pool
- ✅ Understand what happens when the NAT pool runs out
- ✅ Remove Dynamic NAT and switch to **PAT (NAT Overload)**
- ✅ Verify NAT behavior using connectivity tests
- ✅ Examine and the NAT translation table

---


## 🧪 Lab Tasks

### 🧩 Task 1 – Configure Dynamic NAT
- Configure the correct **inside** and **outside** NAT interfaces on R1
- Translate all traffic from `172.16.0.0/24`
- Create a Dynamic NAT pool using **two public IP addresses**

**📌Note: This limits internet access to only two internal hosts at a time.** 

---

### 🧩 Task 2 – Test Dynamic NAT Behavior
- Ping **google.com** from **PC1** and **PC2**
- Ping **google.com** from **PC3**
- Observe what happens to PC3’s traffic when the NAT pool is exhausted

**📌Note: This demonstrates the main limitation of Dynamic NAT.** 

---

### 🧩 Task 3 – Switch from Dynamic NAT to PAT
- Clear existing NAT translations
- Remove the Dynamic NAT configuration
- Reconfigure NAT using **PAT (overload)** with R1’s public IP address

**📌Note: PAT allows many internal devices to share a single public IP.**

---


