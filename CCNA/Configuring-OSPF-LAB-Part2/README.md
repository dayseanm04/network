# Configuring OSPF – Lab Part 2 🧭🖧

## Topology For Reference

<img width="696" height="349" alt="Topology" src="https://github.com/user-attachments/assets/333e133e-c498-4a12-9425-c888a964ff6a" />

## Summary
This lab focuses on configuring and verifying OSPFv2 across four routers in a single-area design.  
I will configure hostnames, interfaces, loopbacks, OSPF, reference bandwidth, advertise the default route, and examine OSPF Hello messages in Packet Tracer Simulation Mode.  
The tasks listed below come directly from the lab instructions.

## 🗂️ Tasks

### 🧩 Task 1: Configure Hostnames & IP Addresses
Configure the appropriate hostnames and IP addresses on each device.  
Enable router interfaces. (ISPR1 does not need configuration)

### 🎯 Task 2: Configure Loopback Interfaces
Create a loopback interface on each router using a /32 address.

### 🌐 Task 3: Enable OSPF on Router Interfaces
Enable OSPF directly on each router interface.  
Configure passive interfaces as appropriate.

### ⚙️ Task 4: Configure OSPF Reference Bandwidth
Configure the reference bandwidth so a FastEthernet interface has a cost of 100.

### 🚪 Task 5: Configure R1 as an ASBR
Configure R1 as an ASBR that advertises a default route into the OSPF domain.

### 🔍 Task 6: Verify Default Routes on R4
Check the routing table of R4 and identify what default route(s) were added.

### 🛰️ Task 7: Analyze OSPF Hello Messages
Use Simulation Mode to view OSPF Hello messages.  
Identify the fields included in the Hello message.

---

### ✍️ Author Information
Name: Daysean Mensah <br/>
Course/Program: Cisco CCNA Studies <br/>
Lab completion date: Dec 09 2025. <br/>
