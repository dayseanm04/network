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

