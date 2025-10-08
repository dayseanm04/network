# 🧠 Lab Notes & Reflection – VLAN Intro Lab

## 🧩 Lab Summary

In this lab, I learned how to configure VLANs on a Cisco switch, assign ports to specific VLANs, and confiure a cisco 2911 router for inter-VLAN routing.  <br/>
I verified connectivity by performing ping tests within and between different VLANs.
<br/>

Click <a href="https://github.com/dayseanm04/network/blob/main/CCNA/verification-results.md"> Here </a> to view the lab results.

---

## ⚙️ Key Skills Learned

- Creating and naming VLANs on a switch  
- Assigning ports to VLANs using `switchport mode access`  
- Configuring router interfaces for inter-VLAN routing  
- Configuring static IPs and default gateways on PCs  
- Testing connectivity using `ping`command  

---

## 🧠 What I Learned

- I learned how VLANs logically separate networks at Layer 2 to improve security and organization.  
- I also understood how routers enable communication between VLANs at Layer 3.  
- Subnetting is important when it comes to dividing a network.

---

## 🧱 Challenges Faced

- I initially misconfigured one of the VLANs on the switch. 
- I used the `show vlan brief` command which helped me identify the problem.
- The problem was that I didnt include the g1/1 interface on the switch when I was configuring vlan10 range
- note that g1/1 on the switch is the interface connected to the router on g0/1  
- I also had to remember to use `no shutdown` on router interfaces to bring them up.

---

## 🧰 Verification & Testing

- I verified the network by pinging devices in the same VLAN, different VLANs, and the default gateways.  
- All pings were successful after the final configuration, confirming that inter-VLAN routing was working correctly.

---

## 🚀 Final Thoughts

- This lab helped me gain hands-on experience with VLAN configuration and router setup in a practical environment.  
- I now feel more comfortable troubleshooting Layer 2 and Layer 3 connectivity issues.
- In this lab I used 3 seperate interfaces for each VLAN  on the router what if I have 10 VLANs? This will be a problem because it means that I will need 10 seperate physical connection for each vlan(routers dont usally have multiple ports like a switch does). But with subinterfaces I can assign multiple interfaces to a single physical interface
---

## 🏁 Next Steps

- Learn about **VLAN trunking (802.1Q)**  
- Configure subinterfaces for the VLANs instead of using a multiple seperate interfaces for each VLAN 

---
