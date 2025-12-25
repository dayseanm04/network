# 💻 Task 4 – Request DHCP Addresses on PC1 and PC2 (ipconfig /renew)

## 🎯 Goal
Use the CLI on **PC1** and **PC2** to force each PC to request an IP address from the DHCP server (R2). Then verify they received the correct:
- ✅ IP Address
- ✅ Subnet Mask
- ✅ Default Gateway
- ✅ DNS Server


## Topology For Reference

<img width="645" height="285" alt="Topology" src="https://github.com/user-attachments/assets/21f639d4-6d6f-4952-9de3-d255df077e99" />

---

## 🗺️ Expected output

| PC | Subnet | Expected Default Gateway | Expected DNS |
|----|--------|--------------------------|--------------|
| PC1 | `192.168.1.0/24` | `192.168.1.1` | `8.8.8.8` |
| PC2 | `192.168.2.0/24` | `192.168.2.1` | `8.8.8.8` |


### On PC1 🖥

**Open Command Prompt on PC1**

### 1️⃣ Request a DHCP Address (Renew)

```bash
ipconfig /renew
```

<img width="665" height="251" alt="PC1-IP-CONFIG-RENEW" src="https://github.com/user-attachments/assets/f40a2b32-1789-4450-b17c-36498901b4c4" />


### On PC2 🖥

**Open Command Prompt on PC1**

### 1️⃣ Request a DHCP Address (Renew)

```bash
ipconfig /renew
```

<img width="751" height="311" alt="PC2-IP-CONFIG-RENEW" src="https://github.com/user-attachments/assets/a69d6582-542c-4788-abd2-83428816b802" />

---

### 2️⃣ Verify PC1 Settings

```bash
ipconfig /all
```

<img width="932" height="434" alt="PC1-ipconfig-all" src="https://github.com/user-attachments/assets/7679eb4a-b334-464b-b08d-769945e79d57" />


### 2️⃣ Verify PC2 Settings

```bash
ipconfig /all
```

<img width="968" height="433" alt="PC2-ipconfig-all" src="https://github.com/user-attachments/assets/a46a30b7-2314-4c1e-8503-6a29f2a7415f" />


## 🔍 Verify on R2

### 3️⃣ Check DHCP Bindings

```bash
show ip dhcp binding
```

<img width="806" height="138" alt="T4-show-R2-dhcp-binding" src="https://github.com/user-attachments/assets/d3bbd7df-7c04-4374-b060-e6706cfc3e1b" />



