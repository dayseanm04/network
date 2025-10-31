# DTP & VTP Lab reflection.md
> Personal reflection and summary of the **Dynamic Trunking Protocol (DTP)** and **VLAN Trunking Protocol (VTP)** lab.

---

## 🧠 Summary

This lab focused on configuring and understanding **DTP (Dynamic Trunking Protocol)** and **VTP (VLAN Trunking Protocol)** across multiple Cisco switches.  

I learned how to configure trunk connections, manage VLANs across a network, and control the propagation of VLAN information using different VTP modes.  

The lab consisted of five main tasks:
1. Configuring trunk ports and disabling DTP on their interfaces.  
2. Setting up a VTP domain and creating VLANs in server mode.  
3. Operating a switch in VTP Transparent mode and observing local VLAN creation behavior.  
4. Configuring a switch as a VTP Client and verifying VLAN synchronization.  
5. Assigning access ports to proper VLANs and confirming that DTP is disabled on those ports.  

---

## 🔍 Key Concepts Learned

### 🧩 Dynamic Trunking Protocol (DTP)
- DTP automatically negotiates trunking between switches.  
- Using the command `switchport nonegotiate` disables DTP to prevent unwanted trunk formation.  
- It is a good security practice to disable DTP on all access ports.  

### 🌐 VLAN Trunking Protocol (VTP)
- VTP allows VLANs to be distributed across switches in the same domain.  
- **VTP Server Mode**: Creates and advertises VLANs.  
- **VTP Client Mode**: Receives VLANs but cannot create or modify them.  
- **VTP Transparent Mode**: Keeps VLANs local and forwards VTP messages without participating in synchronization.  
- All switches must share the same **VTP domain name** for synchronization to work.  

### ⚙️ VLAN Management
- Proper VLAN assignments isolate broadcast domains and improve network segmentation.  
- Each switchport was manually assigned as an **access port** to its corresponding VLAN, ensuring DTP was disabled.  
- Verifying VLAN databases and trunk configurations with `show vlan brief`

---

## 📈 Observations

- When DTP is **enabled by default**, it can automatically attempt to form trunks, disabling it provided better control.  
- Only the VTP **server** can create VLANs; clients receive them automatically once synchronized.  
- The **transparent switch** kept VLAN 40 locally, proving that VTP Transparent Mode does not update the VLAN database on other switches.  
- Attempting to configure VLAN 50 on SW3 (a **client switch**) failed, because it's operating as a client.  
- After configuration, DTP was confirmed **disabled** on all access ports.

---

## 💡 Lessons Learned

- Always verify trunk configurations and DTP negotiation status after setup.  
- Understanding VTP modes is essential for preventing unintended VLAN propagation or overwrites.  
- Consistency in **domain names** and **VTP versions** is critical for VLAN synchronization.  
- Disabling DTP on access ports improves network security.  

---

## 🧾 Conclusion

- This lab provided valuable hands-on experience in managing VLANs and switch interconnections using Cisco IOS.
- It reinforced the importance of understanding both **VTP** and **DTP** when designing scalable and secure layer 2 networks.
- By completing this lab, I now have a good understanding of VLAN propagation, trunk management, and the best practices for switch configuration.
