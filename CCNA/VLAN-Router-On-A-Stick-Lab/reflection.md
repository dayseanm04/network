# 📝 VLAN Lab  Notes & Reflection
Personal summary and reflection for the **VLAN, Trunking, and Router-on-a-Stick (ROAS)** lab.  

---

## 🧠 Lab Summary
In this lab, I configured VLANs, trunk links, and  Router-on-a-Stick to enable communication between multiple VLANs using a single router interface. The main goal was to understand how VLANs segment a network and how inter-VLAN routing allows communication between them.

**Key areas covered:**
- VLAN creation and port assignments on multiple switches  
- Trunk configuration between switches  
- Router subinterfaces for inter-VLAN routing  
- Inter-VLAN connectivity testing and troubleshooting

---

## 💡 What I Learned
- **VLANs** help logically separate networks within the same switch, improving security and limiting broadcast domain.  
- **Trunks** carry multiple VLANs over a single link using **802.1Q encapsulation**.  
- **Native VLANs** carries untagged traffic, and mismatches can cause communication issues.  
- **Router-on-a-Stick (ROAS)** uses subinterfaces on one physical interface to route between multiple VLANs.  
- **Inter-VLAN routing** allows devices in different VLANs to communicate through the router.

---

## ⚙️ Troubleshooting Experience
While testing, I learned to:
- Check VLAN assignments using `show vlan brief`.  
- Use `show interfaces trunk` to verify which VLANs are allowed and active.  
- Confirm router subinterfaces with `show ip interface brief`.  
- I noticed that the **first ping** failed because of **ARP resolution**.  

---

## 🔍 Key Takeaways
- Always make sure VLANs exist on all switches before trunking.  
- Only allow the required VLANs on a trunk link.  
- The router’s subinterface IP address serves as the **default gateway** for that VLAN.  
- Save configurations frequently using `write memory`.  
- Verification commands are just as important as configuration.

---

## 💭 Reflection
This lab helped me better understand how VLANs, trunking, and routers work together. And to always verifiy the commands with **show**.
