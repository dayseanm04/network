# 🧠 Reflection on Multilayer Switching Lab

---

## 📘 Summary
- In this Multilayer Switching Lab, I replaced a  **Router-on-a-Stick (ROAS)** configuration (From <a href="https://github.com/dayseanm04/network/tree/main/CCNA/VLAN-Router-On-A-Stick-Lab"> VLAN-ROAS-LAB</a>) with
- **multilayer switch** to perform inter-VLAN routing.
- The lab involved creating a **Layer 3 point-to-point link** between the router and the switch, configuring **Switch Virtual Interfaces (SVIs)** for each VLAN, and verifying both **inter-VLAN communication** and **Internet connectivity**.
- Each VLAN was assigned its own subnet, and by enabling **IP routing** on the multilayer switch, it could route traffic internally between VLANs without relying on the router for inter-VLAN routing.
- Finally, I configured a default route on the switch (SW2) to allowe Internet traffic to be forwarded to the router (R1).

---

## 💡 Reflection
This lab helped me understand how **multilayer switches** combine the capabilities of both switches and routers.  
Unlike the ROAS configuration, which requires multiple subinterfaces on a router, the multilayer switch performs **Layer 3 routing directly**, improving network efficiency and reducing dependency on the router for local VLAN traffic.

I also learned how to:
- Change a switchport to a **Layer 3 interface** using the `no switchport` command.  
- Create and configure **SVIs** to serve as gateways for each VLAN.  
- Use **default routes** to enable Internet access beyond local networks.  
- Verify routing and connectivity using ping tests between VLANs and to external networks.

Completing this lab gave me a better understanding of **inter-VLAN routing**, **IP addressing**, and how **Layer 3 switching** simplifies modern enterprise network designs.  

---

## 🧠 Lessons Learned
- **Multilayer switches** can perform both switching and routing, making them more efficient for inter-VLAN communication.  
- **SVIs** act as logical interfaces that replace the need for router subinterfaces in a ROAS configuration.  
- Enabling **IP routing** on the switch is essential for Layer 3 functionality.  
- Proper **default route configuration** allows internal VLANs to reach external networks.  
- Testing with pings across VLANs and to public IPs is a reliable way to confirm routing success.  

---

## 🏁 Conclusion
- The key takeaway from this lab was the importance of **Multilayer Switch** in network.
- By migrating from ROAS to a multilayer switch, I learned how to implement scalable, high-performance inter-VLAN routing using SVIs on a multilayer switch.
- The successful test results confirmed that the network is fully functional, with seamless connectivity between VLANs and to the Internet. 🚀
