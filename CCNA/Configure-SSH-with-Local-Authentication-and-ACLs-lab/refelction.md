# 🧠 Reflection - Configure SSH with Local Authentication and ACLs Lab

## 📌 Lab Summary

In this lab, I configured **secure remote management using SSH** on a newly added switch (**SW2**). The lab started with an **initial console-based setup**, which included assigning a hostname, creating local user credentials, configuring a management IP address on **VLAN 1**, and setting a default gateway. This initial access was essential because the switch had no prior configuration.

After the basic setup, I secured **console access** by requiring **local authentication** and configuring an **exec timeout**, ensuring inactive sessions automatically disconnect. Finally, I enabled **SSH-only remote access**, generated **RSA keys**, and restricted management access using an **access control list (ACL)** so that only an authorized host (**PC1**) could connect to the switch remotely.

## Reference Topology

<img width="545" height="224" alt="topology" src="https://github.com/user-attachments/assets/ae47e659-6807-4ae7-9c97-e89aa8e4ebba" />

---


