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

```bash
ipconfig /renew
```

<img width="665" height="251" alt="PC1-IP-CONFIG-RENEW" src="https://github.com/user-attachments/assets/f40a2b32-1789-4450-b17c-36498901b4c4" />


### On PC2 🖥

**Open Command Prompt on PC1**

```bash
ipconfig /renew
```

<img width="751" height="311" alt="PC2-IP-CONFIG-RENEW" src="https://github.com/user-attachments/assets/a69d6582-542c-4788-abd2-83428816b802" />
