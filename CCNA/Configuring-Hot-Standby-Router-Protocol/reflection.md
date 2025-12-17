# HSRP Refletion

## 📝 Summary
In this lab, I configured and tested **HSRPv2** to provide default gateway redundancy for end devices.  
The lab focused on verifying connectivity, implementing HSRP with priorities and preemption, configuring a virtual IP (VIP) as the default gateway, and testing failover and recovery behavior.  
By simulating router failures and recoveries, I was able to observe how HSRP maintains network availability.

---

## 💡 What I Learned

### 🔹 Understanding HSRP and Gateway Redundancy
I learned how HSRP allows multiple routers to share a virtual default gateway, ensuring that hosts do not lose connectivity when a router fails.  
The concept of an **Active** and **Standby** router became clearer through hands-on testing.

### 🔹 HSRPv2 Configuration and Priorities
Configuring HSRPv2 showed me how router **priority values** determine which router becomes Active.  
Raising R1’s priority and lowering R2’s priority helped me understand how HSRP elections work.

### 🔹 Preemption Behavior
By enabling preemption, I learned that a router with a higher priority can reclaim the Active role when it comes back online.  
Testing this behavior helped me understand when preemption is useful and how it affects network stability.

### 🔹 Virtual IP and Virtual MAC Address
Configuring the VIP as the default gateway on the PCs show me that when the active router goes off the standby router takes it place  
Checking the ARP table showed that the VIP maps to a **virtual MAC address**, not the physical MAC of a router.

### 🔹 Failover and Recovery Testing
Turning off the Active router and observing traffic fail over to the Standby router demonstrated how HSRP provides seamless redundancy.  
Turning the router back on and checking whether it resumed the Active role reinforced how priority and preemption control recovery behavior.

---

