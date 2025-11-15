# 📝 Reflection: Configuring STP (PVST+) Lab

This lab gave me hands-on experience on how Cisco **Per VLAN Spanning Tree Plus (PVST+)** operates in a switched network with VLANs. Working through each task helped me understand how STP makes decisions, how root bridges are elected, and how different configuration influence the network.

---

## 🔍 What I Learned

### ⭐ Understanding Root Bridge Elections  
I learned how STP uses **priority + MAC address** to elect the root bridge. By adjusting the priority using the `root primary` and `root secondary` commands, I saw how easy it is to choose the root switch for specific VLANs.

### 🔀 Load Balancing with PVST+  
Because PVST+ builds a separate spanning tree for each VLAN, I was able to create **load balancing** by configuring SW1 as the root for VLAN 1 and SW2 as the root for VLAN 2. This showed me how to control traffic paths and improve performance.

### ⚖️ How STP Chooses the Root Port  
When I increased the STP cost on SW4, I observed that the switch immediately selected a different root port. This helped me understand how **root path cost** is the main factor in STP port role decisions.

### 🔢 Port Priority as a Tie Breaker  
Changing the port priority on SW1 helped me clearly see that port priority only matters when the **root path cost is equal**. If the cost is different, the priority change has no effect.

### 🛡️ Protecting the Network with PortFast & BPDU Guard  
Enabling PortFast and BPDU Guard on access ports taught me how important these features are. When the port received an unexpected BPDU, BPDU Guard **shuts down the interface**, preventing potential loops. This demonstrated real-world protection for access layer networks.

---

## 📘 Overall Summary

This lab helped me understand:

- How **PVST+ runs separate spanning tree instances** per VLAN  
- How **costs, priorities, and root bridge settings** influence the network topology  
- How **BPDU Guard** protect the network from layer 2 loops
- How **PortFast** imporve efficiency
Overall, the lab improved my confidence in configuring and verifying STP behavior, and gave me practical experience that will be valuable in real network environments.

---

## 🚀 Final Thoughts

STP can seem complex at first, but as I kept reading my notes and doing practice labs, I finally understand the concept. With the right configurations, STP becomes a powerful tool for controlling how traffic flow and keeping the network stable, efficient, and loop-free.
