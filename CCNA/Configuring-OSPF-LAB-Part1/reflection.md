# 📝 Reflection – Configuring OSPF Lab (Part 1)

This lab helped me understand how OSPF operates and how routes are exchanged, advertised, and learned across the network. By configuring hostnames, interfaces, loopbacks, OSPF, passive interfaces, and ASBR default route, I understood of how OSPF forms adjacencies and shares routing information.

---

## 🔍 Summary of the Lab

The lab began with configuring hostnames and IP addressing for R1–R4. After that, I configured loopback interfaces, which act like router “identity” addresses that are always up and provide more stability for routing.

Next, I configured **OSPF process 1** on all routers. I enabled OSPF on each interface using wildcard masks and configured **passive interfaces** on loopbacks (and on R4's LAN interface) to prevent unnecessary Hello packets. The task also required not enabling OSPF on R1’s Internet-facing link, which simulated a common real-world design where only internal interfaces participate in the OSPF domain.

The most important part of the lab was configuring **R1 as an ASBR** (Autonomous System Border Router). After adding a static default route on R1, I used the `default-information originate` command to advertise that default route into OSPF. After doing that, R2, R3, and R4 learned the default route and addded it in their routing tables.

---
