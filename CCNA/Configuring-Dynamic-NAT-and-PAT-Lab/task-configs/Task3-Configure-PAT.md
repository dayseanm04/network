# 🔄 Task 3 – Switch from Dynamic NAT to PAT (NAT Overload)

## 🎯 Goal
Remove the **Dynamic NAT configuration** and replace it with **PAT (Port Address Translation)** so that **all internal hosts** can share **R1’s public IP address** to access the internet. 


## Topology For Reference

<img width="588" height="215" alt="Topology" src="https://github.com/user-attachments/assets/a0ad75ab-6982-416a-8c01-5fd83306f1b0" />

---

## ✅ Configure R1

### 1️⃣ Enter Privileged EXEC Mode

```bash
enable
```

### 2️⃣ Clear Existing NAT Translations

```bash
clear ip nat translations
```

**Note:📌 This removes active translation entries from the NAT tablle.**

### 3️⃣ Enter Global Configuration Mode

```bash
configure terminal
```

### 4️⃣ Remove the Dynamic NAT Configuration

```bash
no ip nat inside source list 1 pool public
```
