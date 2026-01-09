# 🖥️ Task 3 – Test-DHCP-IP-Assignment-from-Client

## 📌 Objective

Test whether **PC1** can successfully receive an IP address from the DHCP server **after DHCP Snooping is enabled**.

I will run `ipconfig /renew` on PC1 and observe:

- ✅ Does PC1 get an IP address?
- ❓ If it fails, why does it fail?

## 🧠 Simple Explanation

DHCP Snooping blocks certain DHCP messages on **untrusted ports**.
If something is wrong, the switch may **drop the DHCP traffic**, causing the client to fail to get an IP address.

## Topology For Reference

<img width="667" height="221" alt="topology" src="https://github.com/user-attachments/assets/0437e21d-9c1c-483d-b25a-dc0aa1e8f15a" />

---
