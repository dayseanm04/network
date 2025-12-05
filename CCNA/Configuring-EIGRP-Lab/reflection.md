# 📝 Reflection – Configuring EIGRP Lab

This lab helped me understand how EIGRP works across multiple routers and how routing decisions are made based on metrics,
feasibility, and load-balancing rules. By configuring interfaces, loopbacks, EIGRP, and unequal-cost load balancing, 
I was able to see how EIGRP builds neighbor relationships and selects the best paths.

---

## 🔍 Summary of the Lab

I began by configuring hostnames and IP addresses on R1–R4 and enabling the correct interfaces. After that, I configured
loopback interfaces on each router so every device had a unique /32 address that EIGRP could advertise.

<br/>

Next, I configured EIGRP AS 100 on all routers. I learned how wildcard masks decide which networks get advertised and how 
passive interfaces prevent unnecessary Hello packets on interfaces that should not form neighbor relationships, like 
loopbacks and LAN-facing ports.

<br/>

The last part of the lab introduced **unequal-cost load balancing**. I used the EIGRP **variance** command on R1 to allow 
it to use multiple paths to reach the 192.168.4.0/24 network, even when those paths do not have equal metrics. 
This helped me understand how EIGRP can efficiently use more bandwidth by allowing backup paths to carry traffic as long as
they meet the feasibility rules.

---

## 📚 What I Learned

### ✔ EIGRP uses metrics to choose the best path  
Each router calculates a **feasible distance (FD)**, which is the total metric of the best path to a destination. The router
also learns the **reported distance (RD)** from neighbors.

### ✔ Feasible Successor (FS) must meet the Feasibility Condition  
A path can only be used for backup routing if:

**Reported Distance (RD) < Feasible Distance (FD)**

This prevents routing loops and ensures that only safe paths are used.

### ✔ Variance enables unequal-cost load balancing  
By configuring a **variance value**, I learned that:
- EIGRP can include additional paths that are **up to “variance × Feasible Distance (FD)**  
- This only works if the path is also a feasible successor  
- Variance does *not* guarantee load balancing — it only allows it

This showed me how EIGRP can use multiple links efficiently instead of relying only on equal-cost paths.

### ✔ How to verify EIGRP behavior  
Commands like:
- show ip eigrp neighbors
- show ip route eigrp
- show ip eigrp topology


helped me understand exactly which paths were being used and why.

---

## 🧠 Overall Reflection

This lab gave me a deeper understanding of how dynamic routing works and how EIGRP selects and balances traffic across 
multiple paths. Seeing how FD, RD, feasible successors, and variance interact made the concepts much easier to understand. 
