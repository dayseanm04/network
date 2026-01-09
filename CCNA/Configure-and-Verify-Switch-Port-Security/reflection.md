# 🧠 Reflection – Configure and Verify Switch Port Security

## 📌 Lab Summary

In this lab, I configured and tested **switch port security** to control which devices are allowed to access the network at **Layer 2**. Different port security policies were applied on two switches to compare how **shutdown** and **restrict** violation modes behave in real scenarios.

By intentionally triggering violations, I was able to observe how switches detect unauthorized MAC addresses and enforce security rules on both **access ports** and **trunk ports**.


## Topology For Reference

<img width="589" height="226" alt="topology" src="https://github.com/user-attachments/assets/2f878ac9-10c8-42ea-bb0a-50beebd42c69" />

---

## 🎯 What I Learned

This lab helped me  understand how **port security protects the network** from unauthorized devices.

- **Shutdown mode** immediately disables the interface when a violation occurs, placing it in an **err-disabled** state.
- **Restrict mode** keeps the interface up but **drops unauthorized traffic** and increases the violation counter.
- **Sticky MAC learning** allows the switch to dynamically learn and save MAC addresses without manual configuration.
- Trunk ports can use port security, but they must allow **multiple MAC addresses** because they carry traffic from other switches.

---

## 🔍 Key Observations

- Port security behavior depends heavily on the **violation mode** used.
- Access ports are typically configured more **strictly** than trunk ports.
- Packet Tracer requires **manual recovery** of err-disabled ports using `shutdown` and `no shutdown`.
- The `show port-security` and `show port-security interface` commands are essential for verification and troubleshooting.
