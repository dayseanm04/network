# 🌐 Floating Static Routes Lab

This lab focuses on how floating static routes provide backup connectivity when a primary OSPF route fails. Enterprise A uses OSPF between R1 and R2, and the goal is to ensure PC1 can still reach SRV1 even if the direct link between the R1 & R2 goes down. The lab walks through verifying routing behavior, configuring backup floating static routes, and testing failover.

## Topology For Reference:
<img width="653" height="383" alt="topology" src="https://github.com/user-attachments/assets/ecf85e25-687b-419f-aaad-b4d11e150906" />


## 📝 Lab Summary

- Enterprise A is using **OSPF** as its dynamic routing protocol.
- Under normal conditions, PC1 reaches SRV1 through the primary OSPF path.
- I configure a floating static route (with higher administrative distance) on both R1 and R2 so it only activates if OSPF fails.
- When the R1 or R2 link is shut down, the floating static route automatically enters the routing table.
- PC1 continues to reach SRV1 using the backup path through the ISP.

## ✅ Tasks Completed

### **🔍 Task 1: Verify Routing**
- Checked routing tables on R1 and R2.
- Identified OSPF as the dynamic routing protocol being used.
- Verified the path PC1 uses to reach SRV1 and the Internet (1.1.1.1).
- Confirmed connectivity by pinging both SRV1 and 1.1.1.1.

### **🛠️ Task 2: Configured Floating Static Routes**
- Configured floating static routes on R1 and R2 with an Admistrative Distance of 115.
- Confirmed that the routes do **not** appear initially because OSPF is preferred.

### **⚠️ Task 3: Simulate Link Failure**
- Shut down the G0/2/0 interface on R1.
- Observed floating static routes entering the routing table.
- Verified PC1 can still ping SRV1 through the backup path.

