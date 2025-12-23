# 📝 Reflection – Configuring Extended ACLs Lab

## 📘 Lab Summary
- This lab focused on configuring **extended Access Control Lists (ACLs)** to control traffic between networks and servers.
- Each task required blocking **specific traffic** (hosts or services) while allowing all other communication.
- The lab simulated **real-world security policies**, such as restricting access to DNS or web services without shutting down entire networks.

## 🧠 What I Learned

- **Extended ACLs provide more control** than standard ACLs because they can filter based on:
  - Source IP address
  - Destination IP address
  - Protocol (TCP/UDP)
  - Port numbers (DNS, HTTP, HTTPS)
- **ACL placement matters**:
  - Extended ACLs should be applied **close to the source** to prevent unwanted traffic early.
- **Order of ACL rules is critical**:
  - ACLs are processed top to bottom.
  - There is an **implicit deny** at the end.
  - A final `permit` statement is needed to avoid blocking all traffic.
- Blocking both **TCP and UDP for DNS** is necessary to fully stop DNS communication.

---

## 🧪 Testing & Verification
- I verified each ACL using:
  - `ping` tests to confirm blocked communication
  - `nslookup` to test DNS access
  - Web browser tests for HTTP/HTTPS access
  - `show access-lists` to check match counters
- Match counters helped confirm that the correct ACL rules were being used.

---

## 🔐 Real-World Importance
- This lab reflects tasks that network administrators perform in real environments, such as:
  - Limiting access to sensitive servers
  - Blocking specific services without affecting the entire network
  - Enforcing security policies at the router level

---
