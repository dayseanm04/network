# 📝 Reflection – Configuring OSPF Lab (Part 1)

This lab helped me understand how OSPF operates and how routes are exchanged, advertised, and learned across the network. By configuring hostnames, interfaces, loopbacks, OSPF, passive interfaces, and ASBR default route, I understood of how OSPF forms adjacencies and shares routing information.

---

## 🔍 Summary of the Lab

The lab began with configuring hostnames and IP addressing for R1–R4. After that, I configured loopback interfaces, which act like router “identity” addresses that are always up and provide more stability for routing.

Next, I configured **OSPF process 1** on all routers. I enabled OSPF on each interface using wildcard masks and configured **passive interfaces** on loopbacks (and on R4's LAN interface) to prevent unnecessary Hello packets. The task also required not enabling OSPF on R1’s Internet-facing link, which simulated a common real-world design where only internal interfaces participate in the OSPF domain.

The most important part of the lab was configuring **R1 as an ASBR** (Autonomous System Border Router). After adding a static default route on R1, I used the `default-information originate` command to advertise that default route into OSPF. After doing that, R2, R3, and R4 learned the default route and addded it in their routing tables.

---

## 📚 What I Learned

### ✔ How to configure OSPF 
I practiced enabling OSPF on different interfaces using wildcard masks and ensuring each router participated in the same OSPF area.

### ✔ The purpose of passive interfaces  
Loopback interfaces and internal LAN interfaces should not form adjacencies, so configuring them as passive helps reduce unnecessary OSPF traffic.

### ✔ How OSPF handles loopback interfaces  
Loopbacks are treated as host routes (/32) and are useful for router identification and testing connectivity.

### ✔ What an ASBR is and how default routes are advertise  
I learned that for a router advertise a default route into OSPF, it must already have a default route in its routing table.  
Once that condition is met, `default-information originate` successfully advertises it.

### ✔ How to verify routing behavior 
- show ip route
- show ip protocols

helped confirm whether OSPF was enabled on the correct interfaces and whether each router learned the default route as expected.

---

## 🧠 Overall Reflection

This lab strengthened my understanding of OSPF configuration and how routers share routes within an OSPF domain. Seeing how default routes propagate from an ASBR to internal routers made the routing logic clear. I also gained experience with wildcard masks, passive interfaces, interface activation, and verifying routing tables.  

Overall, this lab was a strong introduction to how OSPF networks are designed and how routing information moves from one router to another.

