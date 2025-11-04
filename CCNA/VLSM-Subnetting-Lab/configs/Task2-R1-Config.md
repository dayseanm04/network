# 🚀 R1 Task2 Configuration

## Objective: Configure LAN Interfaces on R1 and Point-to-Point Connection to R2
---

### Topology for reference
<img width="676" height="314" alt="TPR2" src="https://github.com/user-attachments/assets/623a4fdb-c78a-4821-bc35-66545e00aa68" />



---

## 📊 Subnets Table

| LAN              | Subnet | Subnet Mask         | First Usable IP  | Last Usable IP   | Default Gateway (Router IP) |
|-------------------|----------------|---------------------|-----------------|-----------------|-----------------------------|
| **LAN2 (64 hosts)** | 192.168.5.0/25     | 255.255.255.128 | 192.168.5.1     | 192.168.5.126   | 192.168.5.126              | 
| **LAN1 (45 hosts)** | 192.168.5.128/26   | 255.255.255.192 | 192.168.5.129   | 192.168.5.190   | 192.168.5.190              |
| **Point-to-Point**  | 192.168.5.240/30   | 255.255.255.252 | 192.168.5.241   | 192.168.5.242   | R1: 192.168.5.241 / R2: 192.168.5.242 |

---

##  R1 Interface Configuration Table

| Interface              | IP Address | Subnet Mask         | Description  | 
|-------------------|----------------|---------------------|-----------------|
| **G0/1** | 192.168.5.126     | 255.255.255.128 | LAN2 Connection |
| **G0/0** | 192.168.5.190   | 255.255.255.192 | LAN1 conection   | 
| **G0/0/0** | 192.168.5.241   | 255.255.255.252 | P2P to R2   |

---

## 🛠️ Step-by-Step R1 Configuration

### 🔓 Step 1: Enter Global Configuration Mode
```bash
enable
configure terminal
```

## 🌐 Step 2: Configure LAN2 Interface (GigabitEthernet0/1)
```bash
interface g0/1
ip addr 192.168.5.126 255.255.255.128
no shutdown
exit
```

## 🌐 Step 3: Configure LAN1 Interface (GigabitEthernet0/0)
```bash
interface g0/0
ip addr 192.168.5.190 255.255.255.192
no shutdown
exit
```

## 🔗 Step 4: Configure Point-to-Point Interface (GigabitEthernet0/0/0)
```bash
interface g0/0/0
ip address 192.168.5.241 255.255.255.252
no shutdown
exit
```
## Verify Config
```bash
show ip int brief
```

### Expected output ✅
<img width="816" height="148" alt="R1-show-int" src="https://github.com/user-attachments/assets/604fd4c3-329e-4fa6-99f3-4e60f91e3cd5" />

