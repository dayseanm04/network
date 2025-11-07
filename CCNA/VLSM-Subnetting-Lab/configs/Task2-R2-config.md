# 🚀 R2 Task2 Configuration

---

### Topology for reference

<img width="677" height="314" alt="TPR2" src="https://github.com/user-attachments/assets/a80c2c94-2d50-4653-ac54-dcde0a05c778" />


---

## 📊 Subnets Table

| LAN              | Subnet | Subnet Mask         | First Usable IP  | Last Usable IP   | Default Gateway (Router IP) |
|-------------------|----------------|---------------------|-----------------|-----------------|-----------------------------|
| **LAN3 (14 hosts)** | 192.168.5.192/27   | 255.255.255.224 | 192.168.5.193   | 192.168.5.222   | 192.168.5.222              |
| **LAN4 (9 hosts)**  | 192.168.5.224/28   | 255.255.255.240 | 192.168.5.225   | 192.168.5.238   | 192.168.5.238              |
| **Point-to-Point**  | 192.168.5.240/30   | 255.255.255.252 | 192.168.5.241   | 192.168.5.242   | R1: 192.168.5.241 / R2: 192.168.5.242 |

---

##  R2 Interface Configuration Table

| Interface              | IP Address | Subnet Mask         | Description  | 
|-------------------|----------------|---------------------|-----------------|
| **G0/1** | 192.168.5.238     | 255.255.255.240 | LAN4 Connection |
| **G0/0** | 192.168.5.222   | 255.255.255.224 | LAN3 Conection   | 
| **G0/0/0** | 192.168.5.242   | 255.255.255.252 | P2P to R1   |

---

## 🛠️ Step-by-Step R2 Configuration

### 🔓 Step 1: Enter Global Configuration Mode
```bash
enable
configure terminal
```

## 🌐 Step 2: Configure LAN4 Interface (GigabitEthernet0/1)
```bash
interface g0/1
ip addr 192.168.5.238 255.255.255.240
no shutdown
exit
```

## 🌐 Step 3: Configure LAN3 Interface (GigabitEthernet0/0)
```bash
interface g0/0
ip addr 192.168.5.222 255.255.255.224
no shutdown
exit
```

## 🔗 Step 4: Configure Point-to-Point Interface (GigabitEthernet0/0/0)
```bash
interface g0/0/0
ip address 192.168.5.242 255.255.255.252
no shutdown
exit
```
## Verify Config
```bash
show ip int brief
```

### Expected output ✅

<img width="789" height="165" alt="R2-ip-int" src="https://github.com/user-attachments/assets/40903491-d30a-4446-8e77-ee2cb2588998" />

