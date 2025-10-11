# 🧠 IPv6 Configuration Lab Reflection & Summary

## 🧾 Lab Summary

In this lab, I configured a **dual-stack network** that supports both **IPv4 and IPv6** communication.  
The IPv4 configuration was already complete, and my task was to add IPv6 addressing across the router and PCs to enable connectivity over both protocols.

The main steps involved:
1. Enabling IPv6 routing on the router (R1).  
2. Assigning appropriate IPv6 addresses to each router interface.  
3. Configuring IPv6 addresses and default gateways on all PCs.  
4. Verifying connectivity by performing ping tests between PCs using both IPv4 and IPv6.

By completing these steps, the network became fully functional for both IP versions, demonstrating how dual-stack networks operate in real-world environments.

---

## 🧩 Key Tasks Completed

- Enabled **IPv6 routing** on the router using `ipv6 unicast-routing`.  
- Configured **unique IPv6 addresses** on each router interface:
  - `G0/0 → 2001:DB8:0:1::/64`
  - `G0/1 → 2001:DB8:0:2::/64`
  - `G0/2 → 2001:DB8:0:3::/64`
- Assigned **IPv6 addresses and default gateways** to PCs:
  - PC1 → `2001:DB8:0:1::2/64`, Gateway `2001:DB8:0:1::1`
  - PC2 → `2001:DB8:0:2::2/64`, Gateway `2001:DB8:0:2::1`
  - PC3 → `2001:DB8:0:3::2/64`, Gateway `2001:DB8:0:3::1`
- Verified IPv6 connectivity using **ping tests** between all PCs.

---

## 💡 What I Learned

- **IPv6 addressing structure** is different from IPv4 it uses hexadecimal and is much larger (128-bit).  
- I learned how to **assign IPv6 addresses** to router interfaces and PCs in Packet Tracer.  
- I now understand how to **enable IPv6 routing** on a Cisco router to allow packet forwarding between IPv6 networks.  
- Learned how to **verify configurations** using `show ipv6 interface brief` and **ping tests** to confirm end-to-end communication.

---

## ⚙️ Challenges Faced

- Understanding and typing **IPv6 addresses** correctly was a bit challenging at first due to their long format.  
- Ensuring that each PC’s **default gateway** is correct was crucial for connectivity.

---

## 🚀 Reflection

This lab was an important step in understanding how **IPv6 works alongside IPv4** in a dual-stack environment.  
I learned not only the technical steps but also the reasoning behind IPv6 adoption providing a larger address space and improved efficiency.

Seeing successful **ping replies over IPv6** confirmed that my configuration was correct and working.

---

## 📘 Conclusion

This IPv6 Configuration Lab helped my understanding of:
- IPv6 addressing
- Dual-stack network operation
- Verifying and troubleshooting IPv6 connectivity  
