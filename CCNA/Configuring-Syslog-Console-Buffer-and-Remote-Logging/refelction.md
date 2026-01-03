# 🧠 Reflection - Syslog Console, Buffer, and Remote Logging Lab

## 📌 Lab Summary
In this lab, I configured **Syslog logging** on a Cisco router to observe how system messages are generated and delivered to different logging destinations. The lab began with **console logging**, where interface state changes were used to generate syslog messages and identify their **severity levels**. I then explored how syslog behaves differently when accessing the router remotely using **Telnet (VTY lines)**.

Next, I configured **buffered logging**, allowing syslog messages to be stored locally on the router for later review. Finally, I configured **remote syslog logging** by sending messages to a centralized syslog server (**SRV1**) at the **debugging** level. This demonstrated how enterprise networks centralize logs for monitoring, troubleshooting, and auditing purposes.

## Topology For Reference

<img width="568" height="245" alt="Topology" src="https://github.com/user-attachments/assets/2742761b-077b-4602-ac59-cc579decc1ba" />

---

## 📘 What I Learned
- How to identify **syslog severity levels** and understand their meaning  
- Why syslog messages do not appear by default in **VTY sessions**  
- How to enable syslog display for a remote session using `terminal monitor`  
- How buffered logging stores syslog messages locally on the router  
- How to configure a router to send logs to a **remote syslog server**  
- Why centralized logging is important in real-world network environments  

---

## 🚧 Challenges & Notes
- Understanding why no syslog messages appeared during Telnet access helped reinforce how VTY logging works  
- Packet Tracer limitations required careful observation of log behavior  
- Generating interface up/down events was an effective way to test syslog functionality  
