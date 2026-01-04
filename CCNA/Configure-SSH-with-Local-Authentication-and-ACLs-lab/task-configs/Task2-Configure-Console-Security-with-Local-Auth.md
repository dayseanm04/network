# 🔒 Task 2 - Configure Console Security with Local Auth

## 🎯 Goal

Secure **console access** to **SW2** by requiring **local user authentication** and setting an **exec timeout of 5 minutes**.  
This prevents unauthorized access and reduces the risk of someone leaving an active session open.

## Reference Topology

<img width="545" height="224" alt="topology" src="https://github.com/user-attachments/assets/ae47e659-6807-4ae7-9c97-e89aa8e4ebba" />

---

## 🧩 Step-by-Step Config

### 1️⃣ Enter Global Configuration Mode

On **Laptop1**:

```bash
enable
configure terminal
```

### 2️⃣ Configure Console Line (Line Console 0)

```bash
line console 0
```

### 3️⃣ Enable Local Authentication

```bash
login local
```

### 4️⃣ Set Exec Timeout to 5 Minutes

```bash
exec-timeout 5
```

### 5️⃣ Exit and Save

```bash
end
write memory
```
