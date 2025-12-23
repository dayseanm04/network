# 📝 Reflection – Configuring Static NAT Lab

## 📘 Lab Summary
- In this lab, I configured **Static Network Address Translation (Static NAT)** to allow internal devices to access the internet.
- The lab started by testing connectivity before NAT, which showed that private IP addresses could not reach external networks.
- After configuring Static NAT on the router, internal hosts were able to successfully communicate with public destinations like **8.8.8.8** and **google.com**.

---

## 🧠 What I Learned
- **Static NAT creates a one-to-one mapping** between a private (inside local) IP address and a public (inside global) IP address.
- Internal devices cannot access the internet without NAT because **private IP addresses are not routable** on the public internet.
- Configuring **inside and outside NAT interfaces** is critical for NAT to work.

---

## 🧪 Testing & Verification
- I used `ping` to verify connectivity after NAT was configured.
- The command `show ip nat translations` helped me:
  - See how private IPs were translated to public IPs
  - Confirm that each PC was using its assigned static NAT address
- Clearing the NAT table showed that **only static NAT entries remain**, while temporary entries are removed.
