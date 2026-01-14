# 🔧 Task 2 Configure Internal and Guest Dynamic Interfaces

## 📌 Objective

Create **dynamic interfaces** on **WLC1** for:
-  **Internal WLAN**
- **Guest WLAN**

## 🧠 Simple Explanation

On a Cisco WLC:
- A **WLAN (SSID)** must be mapped to an **interface**
- A **dynamic interface** represents a VLAN/subnet (ex: Internal vs Guest)
- When a client connects to an SSID, the WLC places the client into the **VLAN/subnet** linked to that interface

## Topology For Reference

<img width="491" height="251" alt="topology" src="https://github.com/user-attachments/assets/72d0bdd5-e278-4cca-9727-160600a81eb2" />

---

## 📋 Interface Plan 

| Interface | VLAN ID | IP Address | Subnet Mask | Default Gateway | DHCP Server |
|----------|---------|------------|-------------|-----------------|------------|
| Internal | 100 | 10.0.0.10 | 255.255.255.0 | 10.0.0.1 | 10.0.0.1 |
| Guest | 200 | 10.1.0.10 | 255.255.255.0 | 10.1.0.1 | 10.1.0.1 |


