# 🧩 Multilayer Switching Lab

## Task 4 Internet Connectivity -Test 🌍


### Topology For Reference
<img width="675" height="337" alt="Topology" src="https://github.com/user-attachments/assets/c64f121f-5e60-4e81-8e00-20100f922058" />


---

## 🧩 Objective
Confirm that all PCs across VLANs can reach the Internet by successfully pinging **1.1.1.1**.

---

## 🌐 PC1 (VLAN 10) to Internet 
**PC1 IP Address:** 10.0.0.1  
**Test:** Ping 1.1.1.1  
**Result:** ✅ Successful  

<img width="748" height="378" alt="PC1-internet" src="https://github.com/user-attachments/assets/4dee0a65-d4cb-47e3-a84a-6e92c376ba25" />


---

## 🌐 PC3 (VLAN 30) to Internet
**PC3 IP Address:** 10.0.0.129  
**Test:** Ping 1.1.1.1  
**Result:** ✅ Successful  

<img width="735" height="365" alt="PC3-internet" src="https://github.com/user-attachments/assets/deb41d28-79a0-412f-9b81-f27af504719d" />


---


## 🌐 PC5 (VLAN 20) to Internet 
**PC5 IP Address:** 10.0.0.65  
**Test:** Ping 1.1.1.1  
**Result:** ✅ Successful  

<img width="741" height="383" alt="PC5-internet" src="https://github.com/user-attachments/assets/484d008d-0e9d-4d95-84ca-68519de0ba7b" />


---

## 🌐 PC7 (VLAN 10) to Internet
**PC7 IP Address:** 10.0.0.3  
**Test:** Ping 1.1.1.1  
**Result:** ✅ Successful  

<img width="748" height="374" alt="PC7-internet" src="https://github.com/user-attachments/assets/049b4b1c-8820-42c7-a440-380faaf3b9f3" />

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
