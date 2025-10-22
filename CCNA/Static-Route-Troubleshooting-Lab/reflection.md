# 🧭 Static Route Troubleshooting Lab: Reflection

## 🧩 Summary
This lab focused on **troubleshooting static routing issues** 
Initially, PC1 and PC2 could not communicate due to **multiple routing and interface misconfigurations**.  

Through step-by-step testing and verification using **Cisco Packet Tracer’s Simulation Mode**, the issues were identified and fixed:
- Incorrect next-hop on R1
- Misconfigured exit interface on R2 causing a routing loop
- Wrong interface IP address on R3  

After resolving these issues, **PC1 and PC2 were able to communicate with each other**.

---

## 👀 Observations
- ICMP packets from PC1 to PC2 initially failed because miconfiuration the routers.
- R1 had a wrong next-hop IP for the 192.168.3.0/24 network.
- The routing loop between R1 and R2 occurred because R2 sent traffic back to R1 using the wrong exit interface.
- Once i fixed the loop, the packets reached R3 but stopped due to an incorrect IP address on R3’s G0/0 interface.
- After configuring the correct IP address for R3’s PC1 and PC2 were able to communicate with each other.

---

## 💡 Lessons Learned
1. **Systematic Troubleshooting Matters:**  
   Always start from the source and check each network device step by step. Skipping steps can lead to confusion.

2. **Verify Routing Tables Frequently:**  
   The `show ip route` and `show running-config | include ip route` commands are essential for spotting misconfigured routes.

3. **Check Interfaces First:**  
   Before adjusting routes, confirm that each interface has the correct IP address and subnet mask and is up/up.

4. **Avoid Routing Loops:**  
   Routing loops can occur easily when static routes point to the wrong interface or next-hop. Always verify both direction paths.

5. **Simulation Mode is Powerful:**  
   Packet Tracer’s simulation feature helps visualize packet flow and quickly identify where communication breaks down.

---

## 🧠 Key Takeaways
- Small configuration errors can cause major network connectivity problems.  
- Static routing requires precision.  
- Using a structured troubleshooting process (verify → isolate → correct → test) ensures accurate and efficient problem solving.  
- **Verification after every fix** is crucial to confirm that the issue is resolved before moving to the next step.

---

✨ **Final Result:**  
All routing issues were fixed successfully. PC1 and PC2 can now ping each other 
