# 🚀 EtherChannel Lab

## Topology For Reference
<img width="576" height="295" alt="topology" src="https://github.com/user-attachments/assets/6859cef3-c293-4ed0-8dfe-570631717aca" />

This lab focuses on building **Layer 2 and Layer 3 EtherChannels** using LACP, PAgP, and Static mode. I also configure routing and adjusted the load-balancing methods across the switches. This helped me understand real-world skills in link aggregation, redundancy, and multi-path efficiency. 🌐🔗

## 🧰 Devices Used
- 2 Cisco 2960-24TT switches
- 2 Cisco 3650-24PS switches
- 2 PCs (PC1 & PC2)
- 1 Server (SRV1) 

## 📘 Summary

In this lab I:

- Configured layer 2 EtherChannels using **LACP** and **PAgP**
- Configured a Layer 3 EtherChannel between distribution switches
- Configured Static routing to allow end-to-end connectivity
- Configured the Switches etherchannel load-balancing method to **source-and-destination IP**

### ✅ Task 1: LACP EtherChannel (ASW1 ↔ DSW1)
- Configured Layer 2 EtherChannel using **LACP (mode active)**
- Configured **Port-Channel 1** as a trunk

### ✅ Task 2: PAgP EtherChannel (ASW2 ↔ DSW2)
- Configured Layer 2 EtherChannel using **PAgP (mode desirable)**
- Configured **Port-Channel 1** as a trunk  

### ✅ Task 3: Static Layer 3 EtherChannel (DSW1 ↔ DSW2)
- Configured **Static EtherChannel (mode on)**
- Assigned IP addresses to **port-channel 2**

### ✅ Task 4: Routing to Reach SRV1
- Enabled `ip routing`
- Configured static routes on both DSW1 and DSW2
- Verified PC1 → SRV1 connectivity with ping tests

