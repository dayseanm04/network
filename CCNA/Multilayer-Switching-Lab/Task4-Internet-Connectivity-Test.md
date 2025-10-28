# 🧩 Multilayer Switching Lab

## Task4 Internet Connectivity -Test 🌍


### Topology For Reference
<img width="672" height="333" alt="topology" src="https://github.com/user-attachments/assets/c47bc663-b415-4dac-bc24-1274c349a442" />

---

## 🧩 Objective
Confirm that all PCs across VLANs can reach the Internet by successfully pinging **1.1.1.1**.

---

## 🌐 PC1 (VLAN 10) to Internet 
**PC1 IP Address:** 10.0.0.1  
**Test:** Ping 1.1.1.1  
**Result:** ✅ Successful  
<img width="748" height="379" alt="PC1-internet" src="https://github.com/user-attachments/assets/cc39caf6-eea0-4607-91d1-5b4200038da3" />


---

## 🌐 PC3 (VLAN 30) to Internet
**PC3 IP Address:** 10.0.0.129  
**Test:** Ping 1.1.1.1  
**Result:** ✅ Successful  

<img width="736" height="364" alt="PC3-internet" src="https://github.com/user-attachments/assets/e4b225d3-a846-43f3-821a-220456c866a1" />

---


## 🌐 PC5 (VLAN 20) to Internet 
**PC5 IP Address:** 10.0.0.65  
**Test:** Ping 1.1.1.1  
**Result:** ✅ Successful  

<img width="740" height="384" alt="PC5-internet" src="https://github.com/user-attachments/assets/ea3b9b3b-4ac3-440a-8002-09a458d88d46" />


---

## 🌐 PC7 (VLAN 10) to Internet
**PC7 IP Address:** 10.0.0.3  
**Test:** Ping 1.1.1.1  
**Result:** ✅ Successful  

<img width="746" height="372" alt="PC7-internet" src="https://github.com/user-attachments/assets/88e2e75f-484a-4f4a-a0ce-2e0632e52ab6" />

---

## ✅ Summary
All hosts across VLANs 10, 20, and 30 successfully pinged the Internet address **1.1.1.1** through the multilayer switch and router.

| Device | VLAN | Destination | Result |
|---------|------|--------------|---------|
| PC1 | 10 | Internet (1.1.1.1) | ✅ Success |
| PC3 | 30 | Internet (1.1.1.1) | ✅ Success |
| PC5 | 20 | Internet (1.1.1.1) | ✅ Success |
| PC7 | 10 | Internet (1.1.1.1) | ✅ Success |

---

## 🧾 Conclusion
🌟 All Internet connectivity tests were **successful**.  
This confirms that:
- The **default route** on SW2 is correctly configured.  
- **Layer 3 communication** between SW2 and R1 is functional.  
- All VLANs have **external Internet access**.
