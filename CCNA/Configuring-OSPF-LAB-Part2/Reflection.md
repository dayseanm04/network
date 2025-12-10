# Configuring OSPF Lab Part 2 Reflection


## 📝 Summary  
In this lab, I configured and verified OSPF across a multi-router network.  
The tasks required configuring up router hostnames and interfaces, loopbacks, enabling OSPF on the correct interfaces, adjusting reference bandwidth, configuring an ASBR, verifying external route propagation, and analyzing OSPF Hello messages in Simulation Mode.

---

## 💡 What I Learned

### 🔹 Loopbacks and Router IDs  
Configuing loopbacks helped reinforce how OSPF uses router IDs and why loopbacks provide a stable, reliable ID source.

### 🔹 OSPF Cost and Reference Bandwidth  
By adjusting the reference bandwidth, I learned how OSPF calculates cost and why default values don’t scale well in modern networks. Changing the reference bandwidth ensured consistent and meaningful cost values.

### 🔹 Configuring an ASBR  
I learned how to inject a default route into the OSPF network by configuring R1 as an ASBR. This showed how external routes are advertised and learned by internal routers in the OSPF Area.

### 🔹 Verifying Route Propagation  
Checking R4’s routing table helped confirm that the OSPF domain successfully received the default route, which is important for understanding how external connectivity works in enterprise networks.

### 🔹 OSPF Hello Message Structure  
Using Simulation Mode, I explored OSPF Hello packets and saw real protocol fields such as router ID, DR/BDR, timers, area ID, and neighbor lists.  
This deepened my understanding of how OSPF maintains neighbor relationships.

---

## 🔍 Overall Reflection  
This lab helped strengthen my understanding of OSPF beyond basic configuration. I gained hands-on experience with adjusting the reference bandwidth, OSPF packet analysis, ASBR configuration, and how default routes propagate through the network.  

By completing this lab, I feel more confident in configuring, verifying, and troubleshooting OSPF.
