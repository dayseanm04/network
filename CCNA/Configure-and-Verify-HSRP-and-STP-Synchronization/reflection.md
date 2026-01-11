# 🧠 Reflection – Configure and Verify HSRP and STP Synchronization

## 📌 Lab Summary

In this lab, I configured **HSRP and STP synchronization** across multiple VLANs to ensure efficient traffic flow in a redundant LAN. 

I configured different roles for **VLAN 10** and **VLAN 20** to practice per-VLAN redundancy design.

## Topology For Reference

<img width="618" height="332" alt="Topology" src="https://github.com/user-attachments/assets/67061080-b132-4e96-a33b-6c05489f583e" />

---

## 🎯 What I Learned

- **HSRP** determines the default gateway for hosts
- **STP** determines the Layer 2 forwarding path
- If HSRP and STP are not aligned, traffic can take inefficient paths
- Using different HSRP priorities and STP root roles per VLAN allows **load balancing across switches**
- **Preempt** ensures the intended device regains the Active role after recovery

I also gained hands-on experience configuring **HSRP version 2** and verifying redundancy behavior using show commands.

---

## 🏥 Why This Matters in Real Networks

In enterprise environments such as **hospitals, campuses, and office networks**, inefficient Layer 2/Layer 3 design can cause:
- Increased latency
- Unpredictable traffic paths
- Slower convergence during failures

Synchronizing HSRP and STP is a **best practice** that improves performance, and user experience.

---

## ✅ Overall Takeaway

This lab showed that redundancy is not just about having backup devices—it’s about **designing them correctly**. Aligning HSRP and STP ensures traffic always follows the optimal path while still providing fast failover.

📌 This lab strengthened my understanding of **enterprise LAN redundancy design** and reinforced best practices used in real-world networks.
