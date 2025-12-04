# 📝 Reflection: Floating Static Routes Lab

This lab helped me understand how floating static routes work and why they are important in real network environments. 
By working through each task, I learned how static routes with higher administrative distances behave, and how routers 
react when a primary link goes down.

## 🔍 Summary of the Lab

The lab began by verifying the routing tables on R1 and R2. Both routers were using OSPF as their dynamic routing protocol,
and PC1 was able to reach both SRV1 and the Internet through the normal OSPF-learned paths. <br/>
Next, I configured floating static routes on R1 and R2 with an administrative distance of 115, which is higher than the OSPF 
AD of 110. Because of this, they stayed in the background and were not used unless the primary OSPF routes failed. <br/>
Finally, I tested a failover scenario by shutting down the link between R1 and R2. When the OSPF adjacency went down, the 
OSPF routes were removed from the routing tables, and the floating static routes automatically took over. 
PC1 was still able to reach SRV1, showing that the backup routes were working correctly.

---


