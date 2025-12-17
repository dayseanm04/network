# Task3-Configure-VIP-as-Default-Gateway.md 🌐🖥️

## 🎯 Goal
Configure the **HSRP Virtual IP (VIP)** as the default gateway for **PC1** and **PC2**.  
Then verify connectivity to **8.8.8.8** and check the **ARP table** to see what MAC address maps to the VIP.

## Toplogy For Reference

<img width="624" height="284" alt="toplogy" src="https://github.com/user-attachments/assets/0f9e5564-4206-43af-a79f-1afe60dc7aa1" />

---

## 🖥️ Update PC1 Default Gateway to the VIP

### 1️⃣ Open PC1 IP Configuration
- Click **PC1**
- Go to **Desktop**
- Click **IP Configuration**

### 2️⃣ Set the Default Gateway to the VIP
Set:
- Default Gateway:** `10.0.1.254`

**Reference Bellow:**

<img width="753" height="332" alt="T3-PC1-DG" src="https://github.com/user-attachments/assets/afaff08b-85d9-4229-87a3-213945818cb2" />


### 3️⃣ Test connectivity (PC1)
Open **Command Prompt** and run:

```bash
ping 8.8.8.8
```

### 4️⃣ Check ARP table (PC1)

```bash
arp -a
```

**Expected Output: ✅**

<img width="746" height="215" alt="PC1-ARP" src="https://github.com/user-attachments/assets/b7c66b86-fc1b-4237-8b76-e2d3d3c3eac0" />

