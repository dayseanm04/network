# 📡 Task 1 – Configure DHCP Pools on R2

## 🎯 Goal
Configure **three DHCP pools** on **R2** so it can assign IP addresses to multiple networks, while reserving specific addresses that should NOT be handed out by DHCP.

## Topology For Reference

<img width="645" height="285" alt="Topology" src="https://github.com/user-attachments/assets/21f639d4-6d6f-4952-9de3-d255df077e99" />


### I will configure:
- ✅ **POOL1** for `192.168.1.0/24` (reserve `.1`–`.10`)
- ✅ **POOL2** for `192.168.2.0/24` (reserve `.1`–`.10`)
- ✅ **POOL3** for `203.0.113.0/30` (reserve `.1`)

## 🗺️ DHCP Pool Requirements

### ✅ POOL1 – `192.168.1.0/24`
| Setting | Value |
|--------|------|
| Excluded Range | `192.168.1.1` → `192.168.1.10` |
| DNS | `8.8.8.8` |
| Domain | `jeremysitlab.com` |
| Default Gateway | `192.168.1.1` (R1) |

---
