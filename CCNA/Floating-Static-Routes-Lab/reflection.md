# 📝 Reflection: Floating Static Routes Lab

This lab helped me understand how floating static routes work and why they are important in real network environments. 
By working through each task, I learned how static routes with higher administrative distances behave, and how routers 
react when a primary link goes down.

## 🔍 Summary of the Lab

The lab began by verifying the routing tables on R1 and R2. Both routers were using OSPF as their dynamic routing protocol,
and PC1 was able to reach both SRV1 and the Internet through the normal OSPF-learned paths. <br/> <br/>
Next, I configured floating static routes on R1 and R2 with an administrative distance of 115, which is higher than the OSPF 
AD of 110. Because of this, they stayed in the background and were not used unless the primary OSPF routes failed. <br/> <br/>
Finally, I tested a failover scenario by shutting down the link between R1 and R2. When the OSPF adjacency went down, the 
OSPF routes were removed from the routing tables, and the floating static routes automatically took over. 
PC1 was still able to reach SRV1, showing that the backup routes were working correctly.

---

## 📚 What I Learned

- **How floating static routes work:** A floating static route is simply a static route with a higher AD that activates only when the preferred dynamic route is unsubale due to for example interfawce shutdown etc.
- **How failover happens in real time:** When the main R1–R2 link went down, the routers immediately switched to the backup static routes without manual intervention.
- **The importance of redundancy:** Having a backup route ensures network stability and keeps traffic flowing, even when part of the network fails.
- **How to verify routing behavior:** I practiced using `show ip route`, checking interface states, and testing connectivity using ping and tracert.
---
