# 🧠 Reflection – Upgrade Cisco IOS Using TFTP and FTP

## 📌 Summary

In this lab, I upgraded the **Cisco IOS** on two routers using **TFTP** and **FTP**. I first configured IP addressing and routing to ensure full connectivity, then transferred a new IOS image from a server to each router. After the transfer, I updated the boot settings, reloaded the routers, verified the new IOS version, and cleaned up old IOS files from flash memory.

## Topology For Reference

<img width="545" height="196" alt="topology" src="https://github.com/user-attachments/assets/1895f9fd-c6d2-42f5-ba47-2e54b059671f" />

---

## 🎯 What I Learned

This lab helped me understand how IOS upgrades are performed and why each step matters:

- IOS upgrades require **working network connectivity**
- **TFTP** is simple and fast but does not use authentication
- **FTP** supports usernames and passwords and is more secure
- The **boot system** command controls which IOS image the router loads
- Old IOS files should only be deleted **after confirming** the new IOS is running

I also learned how important it is to verify flash space and save configurations before reloading a router.

---

## 🔍 Key Observations

- File transfers can take time and should not be interrupted
- Verifying the IOS version after reload is critical
- Flash memory management is necessary to avoid storage issues
- Careful planning prevents accidental router downtime



