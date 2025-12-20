# Configuring Standard ACL Lab Reflection.

## 📝 Summary
In this lab, I configured **standard Access Control Lists (ACLs)** to control traffic between multiple networks while maintaining overall network connectivity.  
Before applying any ACLs, I first configured **OSPF** to ensure full communication between PCs and servers.  
I implemented several standard ACL policies to selectively permit or deny traffic based on **source IP addresses**.

### 🔹 How Standard ACLs Work
I learned that standard ACLs only filter traffic based on the **source IP address**, which limits how precisely they can control traffic.  
Because of this, placement of standard ACLs is critical.

### 🔹 Proper ACL Placement
This lab made me understand the rule of placing **standard ACLs as close to the destination as possible**.  
Applying ACLs on the correct router interface and in the correct direction prevented unintended traffic from being blocked.

