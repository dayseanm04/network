# 🛡️ Configure and Verify Dynamic ARP Inspection (DAI)

## 📌 Summary

In this lab I focused on securing the network at layer 2 using **Dynamic ARP Inspection (DAI)**.  
DAI protects the network from **ARP spoofing and ARP poisoning attacks** by validating ARP packets against trusted sources.

To make DAI work correctly, the network is first configured with **DHCP Snooping**, which provides the IP-to-MAC bindings used by DAI to verify ARP traffic.

## Topology For Reference

<img width="685" height="260" alt="topology" src="https://github.com/user-attachments/assets/6b428763-7bbc-4f14-aefa-c2624a090abc" />


## 🎯 Lab Objectives

By completing this lab, you will be able to:
- Configure a router as a **DHCP server**
- Enable **DHCP Snooping** on a switche
- Configure **Dynamic ARP Inspection** on switche
- Apply **additional ARP validation checks**
- Secure the network against **ARP spoofing attacks**

---

## 🧪 Lab Tasks Overview

### 🛠️ Task 1 – Configure R1 as DHCP Server

- Create a DHCP pool for the LAN
- Exclude reserved IP addresses
- Set R1 as the default gateway

📌 *Purpose:* Provide trusted DHCP bindings required for DAI validation.

---

### 🔐 Task 2 – Configure DHCP Snooping on SW1 and SW2

- Enable DHCP Snooping on both switches
- Specify the VLAN used for DHCP Snooping
- Ensure interfaces connected to the router or other switches are trusted

📌 *Purpose:* Build a secure IP–MAC binding table used by DAI.

---


