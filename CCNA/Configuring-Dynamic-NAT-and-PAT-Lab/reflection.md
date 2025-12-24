# 📝 Reflection – Configuring Dynamic NAT and PAT Lab

## 📘 Lab Summary
- In this lab, I configured and tested **Dynamic NAT** and **PAT (Port Address Translation)** to allow internal hosts to access the internet.
- The lab started by using **Dynamic NAT with a limited public IP pool**, which showed how NAT can restrict connectivity when addresses run out.
- The lab then transitioned to **PAT**, demonstrating how multiple devices can share a single public IP address efficiently.

---


## 🧠 What I Learned
- **Dynamic NAT uses a pool of public IP addresses**, and each internal host requires its own public IP.
- When the **NAT pool is exhausted**, additional hosts cannot access the internet, even if everything is configured correctly.
- **PAT (NAT Overload)** solves this problem by:
  - Allowing many internal hosts to share one public IP
  - Using **port numbers** to keep sessions unique

 
