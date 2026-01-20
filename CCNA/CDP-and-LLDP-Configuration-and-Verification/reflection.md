# 🧠 Reflection – CDP and LLDP-Configuration and Verification

## 📌 Summary

In this lab, I used **CDP** to discover neighboring devices and document missing topology details like **interfaces and IP addresses**. After understanding the network layout, I disabled CDP on end-host ports and then disabled it globally across all devices. Finally, I enabled **LLDP** and verified neighbors to confirm that device discovery still worked using a vendor-neutral protocol.

## Topology For Reference

<img width="564" height="278" alt="topology" src="https://github.com/user-attachments/assets/cec8d912-5346-4e0a-a7d2-fc793f76f1c1" />

---

## 🎯 What I Learned
- **CDP** is useful for quickly discovering neighbors on Cisco devices and helping document a network.
- Disabling CDP on **access ports** is a good security practice because end devices don’t need discovery information.
- `no cdp run` disables CDP **globally**, which stops all CDP advertisements.
- **LLDP** is vendor-neutral and can be used instead of CDP in mixed environments.
- LLDP requires both:
  - `lldp run` globally
  - `lldp transmit` and `lldp receive` on the correct interfaces
