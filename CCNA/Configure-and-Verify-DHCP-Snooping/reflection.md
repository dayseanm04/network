# 🧠 Reflection – Configure and Verify DHCP Snooping

## 📌 Lab Summary

In this lab, I configured **DHCP Snooping** to understand how switches can protect a network from **unauthorized DHCP activity**.
I first configured a router as a DHCP server, then enabled DHCP Snooping on switches and defined 
**trusted and untrusted interfaces**. By testing DHCP from a client, I observed how security features can intentionally block 
traffic if the configuration is not fully aligned.

The lab also included troubleshooting a DHCP failure and applying a fix so the client could successfully receive an IP address again.

## Topology For Reference

<img width="667" height="221" alt="topology" src="https://github.com/user-attachments/assets/0437e21d-9c1c-483d-b25a-dc0aa1e8f15a" />

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

## 🔍 Key Observations

- Security features can break normal network functions if not properly configured
- Client-side testing (`ipconfig /renew`) is an effective way to verify DHCP behavior
- Switches enforce trust boundaries at **Layer 2**
- Cisco Packet Tracer may limit some logging, but the overall behavior still demonstrates real concepts

---

## 🏥 Why This Matters in Real Networks

In real enterprise environments such as **hospitals, offices, and campuses**, DHCP Snooping is critical because it:

- Protects users from incorrect or malicious IP assignments
- Helps maintain reliable network access
