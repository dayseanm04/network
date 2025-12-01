# Task 4: Configure Static Routing (PCs to SRV1)

In this task, I will:

- Enable **IP routing** on both distribution switches (DSW1 & DSW2) 
- configure **static routes** so the PCs can reach **SRV1**

## Topology For reference
<img width="576" height="295" alt="topology" src="https://github.com/user-attachments/assets/8197f895-46ff-43a6-9edd-6209fdf9ee68" />

## 🌐 Network Overview

| Device / Network            | IP Address / Network       | Notes                                 |
|-----------------------------|-----------------------------|----------------------------------------|
| **PC1 Network**             | `172.16.1.0 /24`            | PC1 is in this network                 |
| **SRV1 Network**            | `172.16.2.0 /24`            | Server is in this network              |
| **L3 EtherChannel (Po2)**   | `10.0.0.0 /30`              | DSW1 & DSW2 is in this network         |
| **DSW1 – Port-Channel 2**   | `10.0.0.1`                  | DSW1 Layer 3 Port Channel IP address   |
| **DSW2 – Port-Channel 2**   | `10.0.0.2`                  | DSW2 Layer 3 Port Channel IP address   |


I will configure routes so that:

- DSW1 knows how to reach **172.16.2.0/24** via DSW2  
- DSW2 knows how to reach **172.16.1.0/24** via DSW1  


## 1️⃣ Enable IP Routing and Configure Static Route on DSW1

#### 🔷 Enter Global config mode on **DSW1**:

```bash
enable
conf t
```

#### 🔷 Enable IP routing (so the switch can act like a router):
```
ip routing
```

#### 🔷 Configure a static route to the SRV1 network
```bash
ip route 172.16.2.0 255.255.255.0 10.0.0.2
end
```

#### ♦️ Verify the route is in the routing table:
```bash
show ip route
```

**Expected Output ✅:**

<img width="807" height="301" alt="T4-DSW1-route" src="https://github.com/user-attachments/assets/8a3719a1-7130-4c4a-a0e3-8a543d563b37" />

**Note: You should see a static route entry for 172.16.2.0/24 pointing to 10.0.0.2.**

## 2️⃣ Enable IP Routing and Configure Static Route on DSW2

#### 🔷 Enter Global config mode on **DSW1**:

```bash
enable
conf t
```

#### 🔷 Enable IP routing (so the switch can act like a router):
```
ip routing
```

#### 🔷 Configure a static route to the SRV1 network
```bash
ip route 172.16.1.0 255.255.255.0 10.0.0.1
end
```

#### ♦️ Verify the route is in the routing table:
```bash
show ip route
```

**Expected Output ✅:**

<img width="812" height="299" alt="T4-DSW2-route" src="https://github.com/user-attachments/assets/3f5c054d-3582-4b38-9215-b05976c5a4fa" />

**Note: You should see a static route entry for 172.16.1.0/24 pointing to 10.0.0.1.**

## 3️⃣ Test Connectivity from PC1 to SRV1

















