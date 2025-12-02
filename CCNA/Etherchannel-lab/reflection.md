# 📝 EtherChannel Lab Reflection

This EtherChannel lab helped me understand how link aggregation works and why it is important. By completing each task, I got hands-on experience configuring different types of EtherChannels, configuring  Layer 2 and Layer 3 port-channels, and verifying how traffic is distributed across bundled links.

---

## 📘 What I Learned

### 🔹 1. How EtherChannel Combines Links
I learned that EtherChannel allows multiple physical links to act as one logical interface. This increases bandwidth and provides redundancy so the network stays up even if one link fails.

### 🔹 2. Differences Between LACP, PAgP, and Static Mode
- **LACP** – An open standard 
- **PAgP** – Cisco’s proprietary negotiation protocol  
- **Static (On)** – No negotiation; both sides must match manually  

Understanding when to use each method is important for compatibility and design.

### 🔹 3. Layer 2 vs. Layer 3 EtherChannel
I learned how Layer 2 EtherChannels are used for trunking between switches, while Layer 3 EtherChannels allow routing between switches using Port-Channel interfaces.

### 🔹 4. How to Configure Static Routing
I configured static routes so PC1 traffic could travel between networks and reach the server (SRV1).

### 🔹 5. Load-Balancing Methods
I discovered that switches have a default load-balancing method (source MAC), and learned how to view and modify it. Changing it to **source-destination IP** provides better distribution across links depending on traffic patterns.

---

## 💡 Overall Takeaways

This lab improved my understanding of:

- Link aggregation  
- Trunking and Layer 2/Layer 3 switching  
- Port-channel configuration and verification  
- Redundancy and bandwidth optimization  
- Static routing and network reachability  

---

## 🎯 Final Thoughts

By the end, I could clearly see how EtherChannel improves network performance and reliability, and how routing and load-balancing tie everything together.

