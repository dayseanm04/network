# Reflection on Static Routing Lab 🖥️🌐

## Topology For Referernce
<img width="695" height="280" alt="Topology" src="https://github.com/user-attachments/assets/7309f665-e425-4695-a771-1bdc14412e18" />



## Lab Summary 📋

In this lab, I configured PCs and routers based on a given network diagram. The main objectives were:

1. Configure IP addresses and gateways for PCs and router interfaces.
2. Configure static routes on routers to enable communication between different networks.
3. Verify connectivity by performing ping tests between PCs.

The lab helped me understand how routers communicate with each other and how static routes are essential for networks that are not directly connected.  

---

## What I Learned 🧠

- How to configure router hostnames, interfaces, and IP addresses.
- How to set default gateways on PCs.
- How to configure static routes to allow communication between separate networks.
- The importance of bidirectional routes: Without routes back to the source, devices can send packets but may not receive replies.
- How to verify routing configuration using `show ip route`.
- How to troubleshoot network connectivity issues using ping tests.  

---

## Router Configuration Overview 🛠️

| Router | Interface | IP Address     | Subnet Mask     | Notes              |
|--------|-----------|----------------|----------------|------------------|
| R1     | G0/0      | 192.168.12.1  | 255.255.255.0  | Connects to R2    |
| R1     | G0/1      | 192.168.1.254 | 255.255.255.0  | Connects to PC1   |
| R2     | G0/0      | 192.168.12.2  | 255.255.255.0  | Connects to R1    |
| R2     | G0/1      | 192.168.13.2  | 255.255.255.0  | Connects to R3    |
| R3     | G0/0      | 192.168.13.3  | 255.255.255.0  | Connects to R2    |
| R3     | G0/1      | 192.168.3.254 | 255.255.255.0  | Connects to PC2   |

---

## PC Configuration Overview 💻

| PC   | IP Address    | Subnet Mask     | Default Gateway |
|------|---------------|----------------|----------------|
| PC1  | 192.168.1.1   | 255.255.255.0  | 192.168.1.254 |
| PC2  | 192.168.3.1   | 255.255.255.0  | 192.168.3.254 |

---

## Static Routes Summary 🚦

| Router | Destination Network | Next Hop IP   |
|--------|-------------------|--------------|
| R1     | 192.168.3.0/24    | 192.168.12.2 |
| R2     | 192.168.1.0/24    | 192.168.12.1 |
| R2     | 192.168.3.0/24    | 192.168.13.3 |
| R3     | 192.168.1.0/24    | 192.168.13.2 |

---

## Ping Test Results ✅

- PC1 ➡️ PC2: Successful  
- PC2 ➡️ PC1: Successful  

> This confirmed that the static routes were correctly configured and bidirectional communication was possible.  

---

## Reflection 💡

This lab was a great hands-on exercise to understand basic network routing. I realized:

- Configuring interfaces and gateways correctly is crucial for connectivity.  
- Static routing requires careful planning to ensure both directions are reachable.  
- Even a small mistake in IP addresses or routes can break communication.  
- Visualization of the network diagram before configuring is very helpful.  
