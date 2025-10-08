# 🧩 Intro to VLAN Lab — CCNA Part 1

## 📘 Overview
This lab introduces the concept of **Virtual Local Area Networks (VLANs)** and demonstrates how to create VLANs, assign devices to them, and configure **inter-VLAN routing** using a router. The goal is to understand how VLANs improve network segmentation and reduce broadcast domains.

---

## 🧠 Learning Objectives
- Understand how VLANs separate traffic within a LAN.
- Configure VLANs on a switch.
- Assign ports and IP addresses to VLANs.
- Enable router-based inter-VLAN routing.
- Verify connectivity between devices in different VLANs.

---
# 🧩 VLAN Lab Summary

The network is divided into three VLANs with their corresponding default gateways.  
**Note:** The default gateway for each VLAN is the **last usable IP address** of the subnet, configured on the router.

| VLAN | Network        | Subnet Mask       | VLAN Name    | Default Gateway |
|------|----------------|-----------------|-------------|----------------|
| 10   | 10.0.0.0/26    | 255.255.255.192 | Engineering | 10.0.0.62      |
| 20   | 10.0.0.64/26   | 255.255.255.192 | HR          | 10.0.0.126     |
| 30   | 10.0.0.128/26  | 255.255.255.192 | Sales       | 10.0.0.190     |


Each VLAN has its own subnet and default gateway, configured on **Router R1**. Inter-VLAN communication is enabled through router-on-a-stick configuration.

---

## 🧾 Tasks

### 1️⃣ Configure the PC's IP Settings
- Configure the **correct IP address and subnet mask** on each PC.  
- Set the **default gateway** to the **last usable address** of the subnet.

### 2️⃣ Connect and Configure the Router (R1)
- Make **three connections** between **R1** and **SW1**.  
- Configure **one interface on R1 for each VLAN**.  
- Use the **gateway addresses** configured on the PCs.

### 3️⃣ Configure the Switch (SW1)
- Assign the correct **interfaces to their respective VLANs**.  
- Include the **interfaces that connect to R1**.  
- **Name the VLANs**:
  - VLAN10 → *Engineering*  
  - VLAN20 → *HR*  
  - VLAN30 → *Sales*

### 4️⃣ Verify Connectivity
- **Ping between PCs** within and across VLANs.  
- Perform a **broadcast ping** from a PC (ping the subnet broadcast address).  
- Observe which devices receive the broadcast using **Packet Tracer’s Simulation Mode**.

---

## ⚙️ Files Included
- `vlan-intro-lab.pkt` – Cisco Packet Tracer file for the lab.  
- `configs/` – Contains router and switch configuration files.  
- `topology.png` – network diagram.

---

## 🧰 Devices Used
- 1 Cisco 2911 Router (R1)  
- 1 Switch (SW1)  
- 6 PCs (PC1–PC6)  

---

## 🧪 Verification
After completing the configuration:
- Devices within the same VLAN can communicate.
- Devices from different VLANs can communicate via router inter-VLAN routing.
- `show vlan brief` and `show ip interface brief` confirm correct setup.

---

## 📚 Key Takeaways
- VLANs isolate traffic logically within a LAN.  
- Each VLAN requires a separate subnet and gateway.  
- Inter-VLAN routing allows communication between VLANs.  
- Proper VLAN configuration enhances performance and security.
