# 🛡️ Configure and Verify Dynamic ARP Inspection (DAI)

## 📌 Summary

In this lab I focused on securing the network at layer 2 using **Dynamic ARP Inspection (DAI)**.  
DAI protects the network from **ARP spoofing and ARP poisoning attacks** by validating ARP packets against trusted sources.

To make DAI work correctly, the network is first configured with **DHCP Snooping**, which provides the IP-to-MAC bindings used by DAI to verify ARP traffic.

## Topology For Reference

<img width="685" height="260" alt="topology" src="https://github.com/user-attachments/assets/6b428763-7bbc-4f14-aefa-c2624a090abc" />

---


