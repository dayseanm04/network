# 🚀 Task-1-Router-configs.md

## Objective configure router interfaces

---

## Topology For Reference
<img width="695" height="280" alt="Topology" src="https://github.com/user-attachments/assets/9bb5387a-481b-4721-83d3-ff9d6468af84" />



## Router Interface Table
| Device | Interface | IP Address | Subnet Mask | Description |
|---------|------------|-------------|--------------|--------------|
| R1 | G0/1 | 192.168.1.254 | 255.255.255.0 | LAN for PC1 |
| R1 | G0/0 | 192.168.12.1 | 255.255.255.0 | Link to R2 |
| R2 | G0/0 | 192.168.12.2 | 255.255.255.0 | Link to R1 |
| R2 | G0/1 | 192.168.13.2 | 255.255.255.0 | Link to R3 |
| R3 | G0/0 | 192.168.13.3 | 255.255.255.0 | Link to R2 |
| R3 | G0/1 | 192.168.3.254 | 255.255.255.0 | LAN for PC2 |

---

## 🛠️ Step-by-Step R1 Configuration

### 🔓 Step 1: Enter Global Configuration Mode
```bash
enable
configure terminal
```

### 🌐 Step 2: Change Router hostame to R1
```bash
hostname R1
```

### 🌐 Step 3: Configure R1 0/1 Interface
```bash
int g0/1
ip address 192.168.1.254 255.255.255.0
no shutdown
exit
```

### 🌐 Step 4: Configure R1 0/0 Interface
```bash
int g0/0
ip address 192.168.12.1 255.255.255.0
no shutdown
exit
```

### 🌐 Step 5: Verify
```bash
show ip int brief
```

### 🌐 Step 6: Save config
```bash
write
```
---

## 🛠️ Step-by-Step R2 Configuration

### 🔓 Step 1: Enter Global Configuration Mode
```bash
enable
configure terminal
```

### 🌐 Step 2: Change Router hostame to R2
```bash
hostname R2
```

### 🌐 Step 3: Configure R1 0/1 Interface
```bash
int g0/1
ip address 192.168.13.2 255.255.255.0
no shutdown
exit
```

### 🌐 Step 4: Configure R1 0/0 Interface
```bash
int g0/0
ip address 192.168.12.2 255.255.255.0
no shutdown
exit
```

### 🌐 Step 5: Verify
```bash
show ip int brief
```

### 🌐 Step 6: Save config
```bash
write
```

---

## 🛠️ Step-by-Step R3 Configuration

### 🔓 Step 1: Enter Global Configuration Mode
```bash
enable
configure terminal
```

### 🌐 Step 2: Change Router hostame to R3
```bash
hostname R3
```

### 🌐 Step 3: Configure R1 0/1 Interface
```bash
int g0/1
ip address 192.168.3.254 255.255.255.0
no shutdown
exit
```

### 🌐 Step 4: Configure R1 0/0 Interface
```bash
int g0/0
ip address 192.168.13.3 255.255.255.0
no shutdown
exit
```

### 🌐 Step 5: Verify
```bash
show ip int brief
```

### 🌐 Step 6: Save config
```bash
write
```
