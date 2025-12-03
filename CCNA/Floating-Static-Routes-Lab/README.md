# 🌐 Floating Static Routes Lab

This lab focuses on how floating static routes provide backup connectivity when a primary OSPF route fails. Enterprise A uses OSPF between R1 and R2, and the goal is to ensure PC1 can still reach SRV1 even if the direct link between the R1 & R2 goes down. The lab walks through verifying routing behavior, configuring backup floating static routes, and testing failover.

## Topology For Reference:
<img width="649" height="379" alt="topology" src="https://github.com/user-attachments/assets/7f281354-4b69-48a1-bf5d-5a134fa97fd0" />

## 📝 Lab Summary

- Enterprise A is using **OSPF** as its dynamic routing protocol.
- Under normal conditions, PC1 reaches SRV1 through the primary OSPF path.
- I configure a floating static route (with higher administrative distance) on both R1 and R2 so it only activates if OSPF fails.
- When the R1 or R2 link is shut down, the floating static route automatically enters the routing table.
- PC1 continues to reach SRV1 using the backup path through the ISP.

## ✅ Tasks Completed
