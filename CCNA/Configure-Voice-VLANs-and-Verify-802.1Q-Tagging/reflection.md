# 🧠 Reflection – Configure Voice VLANs and Verify 802.1Q Tagging

## 📌 Lab Summary
y
In this lab, I configured **voice and data VLANs** on an access switch and used **Router-on-a-Stick (ROAS)** to enable inter-VLAN routing. The main goal was to understand how **voice traffic and data traffic behave differently** on a network, especially in terms of **802.1Q VLAN tagging**.

Using **Packet Tracer Simulation Mode**, I verified how traffic is handled at the frame level by inspecting outbound PDUs for both **PC-to-PC** and **IP phone-to-IP phone** communication.

## Reference Network Diagram

<img width="657" height="253" alt="topology" src="https://github.com/user-attachments/assets/9fa39f57-3919-4563-8206-e8441d628383" />

---

## 🎯 What I Learned

One of the most important takeaways from this lab is that **not all VLAN traffic is tagged the same way**.

- **PC data traffic** sent on access ports is **not tagged**, even though the PC belongs to a VLAN.
- **Voice traffic from IP phones** *is* **802.1Q tagged**, because it uses a **Voice VLAN**.
- A single switch port can safely support **both a PC and an IP phone** by using:
  - `switchport access vlan` for data
  - `switchport voice vlan` for voice

I also reinforced my understanding of **Router-on-a-Stick**, where:
- A single router interface carries multiple VLANs
- Each VLAN is mapped to a **subinterface** with its own IP address and VLAN ID

---

---

## 🚀 Why This Matters in Real Networks

In enterprise environments like **hospitals, offices, and campuses**, voice and data traffic often share the same infrastructure. This lab shows how networks:
- Reduce cabling costs
- Maintain traffic separation
- Prioritize and protect voice communications
