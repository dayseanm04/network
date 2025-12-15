# Troubleshooting OSPF LAB Reflection 🧭

## Topology For Reference

<img width="716" height="333" alt="topology" src="https://github.com/user-attachments/assets/ab9b245c-d477-4ad7-ab00-ec358ff600f2" />

## 📝 Summary
In this lab, I worked on troubleshooting and fixing OSPF issues in a partially pre-configured network.  
Instead of building everything from scratch, the focus was on identifying problems, understanding why they occurred, and applying the correct fixes.  
The lab involved configuring a new serial link, resolving missing routes, fixing OSPF neighbor adjacencies, restoring external connectivity, and examining the OSPF Link-State Database (LSDB).

## 💡 What I Learned

### 🔹 Serial Links and DCE/DTE Roles
I learned how serial links work and why only the DCE side requires a clock rate.  
Verifying the interface with `show controllers` helped confirm which router controlled the clocking.

### 🔹 OSPF Route Advertisement Issues
When only one router had access to a network, I learned how OSPF interface settings can prevent routes from being advertised.  
This understand the importance of matching OSPF network types on connected interfaces.

### 🔹 OSPF Neighbor Formation
I learned that OSPF neighbors will not form if Hello and Dead timers do not match.  
Fixing the timer mismatch on R5 showed how times mismatch can completely block adjacency.

### 🔹 Default Routes and External Connectivity
Restoring connectivity to the external server helped me understand how default routes work and why they must be advertised into OSPF from the edge router.  
Once the default route was injected, internal routers were able to reach external networks.

### 🔹 Understanding the OSPF LSDB
Examining the LSDB helped me understand how OSPF maintains a complete view of the network.  

---

## 🔍 Overall Reflection
This lab improved my troubleshooting skills It showed that OSPF problems are often caused by small mismatches rather than major misconfigurations.  
After completing this lab, I feel more confident troubleshooting OSPF adjacencies, routing issues, and external connectivity.
