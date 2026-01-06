# 📞 Configure Voice VLANs and Verify 802.1Q Tagging

## 📌 Summary

This lab demonstrates how **voice and data traffic are separated using VLANs** and how **802.1Q tagging behaves differently** for PCs and IP phones.

A **Voice VLAN** is configured on access switch ports so that:

- **Data traffic (PCs)** remains **untagged**
- **Voice traffic (IP Phones)** is **tagged with 802.1Q**

Packet Tracer **Simulation Mode** is used to visually verify this behavior.

---

## 🧪 Lab Tasks Overview

### 🛠️ Task 1 - Configure Access Ports for Data and Voice VLANs
- Assign **data VLAN** and **voice VLAN** to switch access ports
- IP phones connect to the switch, with PCs connected through the phones
- The switch informs the phones which VLAN to use for voice traffic

---

### 🔀 Task 2 - Configure Router-on-a-Stick (ROAS)

- Configure the switch-to-router link as a **trunk**
- Create router **subinterfaces** for:
  - Data VLAN
  - Voice VLAN

---

### 🖥️ Task 3 - Verify Data Traffic (PC to PC)
- Use **Simulation Mode**
- Ping **PC2 from PC1**
- Inspect the outbound frame

❓ **Is the traffic VLAN-tagged?**

➡️ No - data traffic sent to PCs is **not tagged**

---

### 📞 Task 4 – Verify Voice Traffic (Phone to Phone)

- Use **Simulation Mode**
- Place a call from **PH1 to PH2**
- Inspect the outbound frame details

❓ **Is the traffic VLAN-tagged?**

➡️ Yes - voice traffic is **tagged with 802.1Q (Voice VLAN)**


---

