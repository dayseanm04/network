# 🔐 Configure DHCP Snooping for DAI

## 📌 Objective

Enable **DHCP Snooping** on **SW1** and **SW2** to build a **trusted IP-to-MAC binding table**.  
These bindings are required for **Dynamic ARP Inspection (DAI)** to validate ARP packets.

---

## 🧠 Simple Explanation

- DHCP Snooping inspects DHCP traffic
- Only **trusted interfaces** are allowed to forward DHCP server messages
- Client-facing ports stay **untrusted by default**
- The switch records **IP–MAC bindings**, which DAI will use later

📌 Think of DHCP Snooping as the **foundation** for DAI.

## Topology For Reference

<img width="685" height="260" alt="topology" src="https://github.com/user-attachments/assets/6b428763-7bbc-4f14-aefa-c2624a090abc" />

---

## 📋 What I Will Configure

- Enable DHCP Snooping globally
- Enable DHCP Snooping for **VLAN 1**
- Disable the DHCP information option (Option 82)
- Trust **uplink interfaces** connected to a router or another switch

---
