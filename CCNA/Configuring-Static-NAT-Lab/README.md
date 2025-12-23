# 🌐 Configuring Static NAT Lab

## 📘 Lab Overview
In this lab, I configured **Static Network Address Translation (Static NAT)** to allow internal hosts to communicate with the internet using **public IP addresses**. Static NAT creates a **one-to-one mapping** between an inside local address and an inside global address.

The lab demonstrates why NAT is required, how static NAT is configured on a router, and how NAT translations behave when traffic is generated and cleared.

## Topology For Reference

<img width="648" height="227" alt="Topology" src="https://github.com/user-attachments/assets/9eff3467-85fb-40f2-a50c-a3eca4d670d2" />

## 🎯 Lab Objectives
By completing this lab, You will be able to:

- ✅ Understand why internal hosts cannot reach the internet without NAT
- ✅ Configure **inside** and **outside** NAT interfaces
- ✅ Create **static NAT mappings** for multiple hosts
- ✅ Verify NAT operation using connectivity tests
- ✅ Interpret and clear the NAT translation table

---

## 🧪 Lab Tasks

### 🧩 Task 1 – Test Connectivity Before NAT
- Attempt to ping **8.8.8.8** from **PC1**
- Observe and document whether the ping succeeds or fails

**📌 This confirms that NAT is required for internet access.**

### 🧩 Task 2 – Configure Static NAT on R1
This task is split into two parts:

#### 🔹 Task 2A – Configure Inside and Outside Interfaces
- Identify which R1 interface connects to the **LAN**
- Identify which R1 interface connects to the **internet**
- Configure the correct NAT roles on each interface

#### 🔹 Task 2B – Comfigure Static NAT Mappings
- Map:
  - PC1 → `100.0.0.1`
  - PC2 → `100.0.0.2`
  - PC3 → `100.0.0.3`
- Verify 

---

### 🧩 Task 3 – Test Connectivity After NAT
- Ping **8.8.8.8** from **PC1**
- Observe whether connectivity is now successful

---

### 🧩 Task 4 – Verify NAT Translations
- Ping **google.com** from:
  - PC1
  - PC2
  - PC3
- Check the NAT translation table on **R1**
- Observe how inside local and inside global addresses are displayed

---

### 🧩 Task 5 – Clear NAT Translations
- Clear the NAT translation table on **R1**
- View the table again and identify which entries remain

---
