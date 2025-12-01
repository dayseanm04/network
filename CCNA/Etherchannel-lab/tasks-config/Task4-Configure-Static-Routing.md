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


