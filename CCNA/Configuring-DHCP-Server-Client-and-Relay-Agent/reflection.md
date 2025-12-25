# 📝 Reflection – Configuring DHCP Server, Client, and Relay Agent Lab

## 📘 Lab Summary
- In this lab, I configured **DHCP services across multiple networks** using routers and PCs.
- I set up **R2 as a centralized DHCP server** with multiple DHCP pools.
- I configured **R1 as both a DHCP client and a DHCP relay agent**, allowing DHCP to work across different subnets.
- Finally, I verified that **PC1 and PC2 successfully obtained IP addresses** from the DHCP server.

## Topology For Reference

<img width="645" height="285" alt="Topology" src="https://github.com/user-attachments/assets/21f639d4-6d6f-4952-9de3-d255df077e99" />

---

## 🧠 What I Learned
- **DHCP simplifies IP address management** by automatically assigning:
  - IP addresses
  - Subnet masks
  - Default gateways
  - DNS servers
- A single router can manage **multiple DHCP pools**, each serving a different subnet.
- **Excluded addresses** are important to prevent DHCP from assigning IPs that should be reserved for routers or servers.
- Routers can act as **DHCP clients**, not just end devices.
- **DHCP relay agents** are required when:
  - The DHCP server is on a different subnet
  - DHCP broadcast messages need to cross routers
- The `ip helper-address` command is critical for forwarding DHCP requests to a remote DHCP server.

---

## 🧪 Testing & Verification
- I used:
  - `ipconfig /renew` on PCs to request DHCP addresses
  - `ipconfig /all` to verify DHCP settings
  - `show ip dhcp binding` on R2 to view the DHCP binding
- I verified that:
  - PC1 and PC2 received IP addresses **outside the excluded ranges**
  - Each PC received the **correct default gateway and DNS server**
  - R1 successfully received an IP address via DHCP on its G0/0 interface

---

## 🌐 Real-World Importance
- This lab reflects real enterprise networks where:
  - DHCP servers are centralized
  - Multiple subnets depend on relay agents
  - Routers dynamically receive addresses from service providers
