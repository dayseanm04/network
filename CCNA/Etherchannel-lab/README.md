# 🚀 EtherChannel Lab

## Topology For Reference
<img width="576" height="295" alt="topology" src="https://github.com/user-attachments/assets/6859cef3-c293-4ed0-8dfe-570631717aca" />

This lab focuses on building **Layer 2 and Layer 3 EtherChannels** using LACP, PAgP, and Static mode. I also configure routing and adjusted the load-balancing methods across the switches. This helped me understand real-world skills in link aggregation, redundancy, and multi-path efficiency. 🌐🔗


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

### ✅ Task 5: Determine the default EtherChannel Load-Balancing method for the switches
- All switches use: **src-mac (Source MAC Address)**

### ✅ Task 6: Configure the switches EtherChannel to load balance based on Source and Destination IP
- with this command: `show etherchannel load-balance`

**Note: ASW means Access Switch and DSW means Distribution Switch**

---

## 🧰 Devices Used
- 2 Cisco 2960-24TT switches
- 2 Cisco 3650-24PS switches
- 2 PCs (PC1 & PC2)
- 1 Server (SRV1) 

---

# 📚 Navigation – EtherChannel Lab

Use the table below to quickly access all parts of the EtherChannel lab, including Packet Tracer files, task-by-task configs, and the lab reflection.

---

## 📂 Repository Navigation Table

| Section | Description | Link |
|--------|-------------|------|
| 🧪 **Pkt-files Folder** | contains the packet tracer file for this lab | [pkt-files/](pkt-files/) |
| 📁 **tasks-config Folder** | Step-by-step configuration guides for each task | [tasks-config](tasks-config/) |
| ✍️ **Reflection** | Summary of what I learned and key takeaways | [reflection.md](reflection.md) |

---


## ✍️ Author Information

**Name:** *Daysean Mensah*  
**Course/Program:** *Cisco CCNA Studies*  
**Lab completion date:** November 29 2025.
