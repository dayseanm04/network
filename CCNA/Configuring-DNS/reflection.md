# 📝 Reflection – Configuring DNS Lab

## Referecnce topology

<img width="626" height="254" alt="Topology" src="https://github.com/user-attachments/assets/090b0b37-f4ba-4bc0-bf54-4d6a0a9cb72d" />


## 📘 Lab Summary
- In this lab, I configured and tested **DNS functionality** across routers and PCs.
- I set up a **default route on R1** so traffic could reach the Internet.
- I configured **PC1, PC2, and PC3** to use an external DNS server (`1.1.1.1`).
- I also configured **R1 to use DNS**, added local **host entries**, and verified name resolution.
- Finally, I used **Simulation Mode** to observe how DNS works behind the scenes when a device pings a website by name.

---

## 🧠 What I Learned
-  Without a DNS server, devices cannot resolve domain names like `youtube.com`.
- A **default route** is essential for DNS and Internet access. Even if DNS is configured correctly, name resolution will fail if traffic cannot leave the network.
- Devices can resolve names in two ways:
  - Using **local host entries** (`ip host`) configured on a router
  - Using an **external DNS server** for Internet domains
- Routers can act as **DNS clients**, not just forward traffic.

---

## 🧪 Simulation Mode Packet analysis
- When PC1 pinged `youtube.com`, I observed multiple message types:
  - **DNS Query** – PC1 asked the DNS server for the IP address
  - **DNS Answer** – The DNS server replied with the IP
  - **ARP** – Used to find the MAC address of the next-hop device
  - **ICMP** – The actual ping packets
- This showed that **DNS happens before ICMP**, which is something not visible in real-time without simulation tools.

---

## 🌐 Real-World Importance
- DNS is one of the most critical services in modern networks.
- Understanding DNS helps with:
  - Troubleshooting connectivity issues
  - Identifying whether problems are related to routing, DNS, or applications
  - Designing reliable enterprise networks
