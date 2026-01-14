# 🧠 Reflection – Configure WLANs Using Cisco Wireless LAN Controller

## 📌 Summary

In this lab, I configured a wireless network using a **Cisco 3504 Wireless Controller**. I accessed the WLC GUI, created **dynamic interfaces**, configured **Internal and Guest WLANs**, secured them with **WPA2-PSK**, and verified connectivity by associating a wireless client to an access point.

The lab helped me understand how wireless networks are **centrally managed** using a controller instead of configuring each access point individually.

## Topology For Reference

<img width="491" height="251" alt="topology" src="https://github.com/user-attachments/assets/72d0bdd5-e278-4cca-9727-160600a81eb2" />

---

## 🎯 What I Learned

This lab helped me learn several important wireless concepts:

- How to access and navigate the **WLC GUI**
- The purpose of **dynamic interfaces** and how they map WLANs to VLANs
- How to create and enable **WLANs (SSIDs)** on a WLC
- How **WPA2-PSK** secures wireless networks
- How to verify wireless connectivity from a client’s perspective

---

## 🔍 Key Observations

- WLANs must be **enabled** before clients can connect
- WLANs must be mapped to the **correct interface**, or clients may get the wrong IP address
- Packet Tracer has **limitations**, especially with DHCP behavior on WLCs

---

## Why This Matters in Real Networks

In enterprise environments such as **campuses and offices**, WLCs are commonly used to:
- Centralize wireless management
- Simplify configuration and troubleshooting
- Separate **internal and guest wireless traffic**
- Apply consistent security settings across access points
