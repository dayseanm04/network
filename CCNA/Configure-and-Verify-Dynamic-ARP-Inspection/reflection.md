# 🧠 Reflection – Configure and Verify Dynamic ARP Inspection

## 📌 Lab Summary
In this lab, I configured **Dynamic ARP Inspection (DAI)** to protect the network from **ARP spoofing and ARP poisoning attacks**. The lab required configuring a DHCP server and enabling **DHCP Snooping**, which provides the trusted IP-to-MAC bindings that DAI relies on.

After the prerequisites were in place, DAI was enabled on the switches and additional validation checks were applied to ensure only legitimate ARP traffic was allowed.

## Topology For Reference

<img width="685" height="260" alt="topology" src="https://github.com/user-attachments/assets/6b428763-7bbc-4f14-aefa-c2624a090abc" />

---


## 🎯 What I Learned

This lab helped me understand how multiple **Layer 2 security features work together**:

- **DHCP Snooping** builds a trusted binding table of IP and MAC addresses
- **Dynamic ARP Inspection** uses those bindings to verify ARP packets
- Only **trusted ports** (router and switch uplinks) should be allowed to foward DHCP Server messages
- Enabling extra validation checks increases protection against spoofed ARP messages

I also learned that DAI is not a standalone feature, it depends on correct DHCP Snooping configuration to function properly.

---


## 🔍 Key Observations

- All switch ports are **untrusted by default**, which improves security
- Incorrect trust configuration can easily break network connectivity
- Packet Tracer may show different rate-limiting behavior compared to real Cisco hardware
- Verification commands like `show ip arp inspection` is useful for troubleshooting

---

