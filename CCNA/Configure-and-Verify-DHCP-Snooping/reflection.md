# 🧠 Reflection – Configure and Verify DHCP Snooping

## 📌 Lab Summary

In this lab, I configured **DHCP Snooping** to understand how switches can protect a network from **unauthorized DHCP activity**.
I first configured a router as a DHCP server, then enabled DHCP Snooping on switches and defined 
**trusted and untrusted interfaces**. By testing DHCP from a client, I observed how security features can intentionally block 
traffic if the configuration is not fully aligned.

The lab also included troubleshooting a DHCP failure and applying a fix so the client could successfully receive an IP address again.

---

## 🎯 What I Learned

This lab helped me understand the purpose and behavior of **DHCP Snooping**:

- DHCP Snooping prevents **rogue DHCP servers** from sending responses to clients
- Only **trusted interfaces** are allowed to forward DHCP server messages
- Client ports remain **untrusted by default**, which improves security
- **DHCP Option 82** can impact DHCP traffic and cause requests to fail
- A small configuration change can restore DHCP functionality while keeping security enabled

I also learned how important it is to test client behavior after enabling security features.

---
