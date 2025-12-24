# 📝 Reflection – Configuring Dynamic NAT and PAT Lab

## 📘 Lab Summary
- In this lab, I configured and tested **Dynamic NAT** and **PAT (Port Address Translation)** to allow internal hosts to access the internet.
- The lab started by using **Dynamic NAT with a limited public IP pool**, which showed how NAT can restrict connectivity when addresses run out.
- The lab then transitioned to **PAT**, demonstrating how multiple devices can share a single public IP address efficiently.

## Topology For Reference

<img width="588" height="215" alt="Topology" src="https://github.com/user-attachments/assets/a0ad75ab-6982-416a-8c01-5fd83306f1b0" />

---

## 🧠 What I Learned
- **Dynamic NAT uses a pool of public IP addresses**, and each internal host requires its own public IP.
- When the **NAT pool is exhausted**, additional hosts cannot access the internet, even if everything is configured correctly.
- **PAT (NAT Overload)** solves this problem by:
  - Allowing many internal hosts to share one public IP
  - Using **port numbers** to keep sessions unique

 ---

## 🧪 Testing & Verification
- I verified Dynamic NAT by pinging `google.com` from multiple PCs and observing when connectivity failed.
- The `show ip nat translations` command helped me:
  - See which internal hosts received public IPs
- After switching to PAT, all PCs were able to access the internet successfully.
- The NAT table showed **one public IP with multiple port-based translations**, confirming PAT was working.

---

## 🌐 Real-World Importance
- Dynamic NAT is useful but **not scalable** for large networks.
- PAT is the most commonly used NAT method in:
  - Home networks
  - Enterprise networks
- Understanding both NAT methods is important for **network designing**.
