# 🖥️ PC Configuration for VLAN Intro Lab

This document outlines the static IP configurations for all PCs used in the **VLAN Intro** lab.  
Each VLAN operates as a separate broadcast domain with its own subnet and default gateway.

---

## VLAN 10 — Engineering

**Network Details:**
- Subnet: `10.0.0.0/26`
- Subnet Mask: `255.255.255.192`
- Default Gateway: `10.0.0.62`

| Device | IPv4 Address | Subnet Mask | Default Gateway |
|---------|---------------|--------------|------------------|
| PC1 | `10.0.0.1` | `255.255.255.192` | `10.0.0.62` |
| PC2 | `10.0.0.2` | `255.255.255.192` | `10.0.0.62` |

---

## VLAN 20 — HR

**Network Details:**
- Subnet: `10.0.0.64/26`
- Subnet Mask: `255.255.255.192`
- Default Gateway: `10.0.0.126`

| Device | IPv4 Address | Subnet Mask | Default Gateway |
|---------|---------------|--------------|------------------|
| PC3 | `10.0.0.65` | `255.255.255.192` | `10.0.0.126` |
| PC4 | `10.0.0.66` | `255.255.255.192` | `10.0.0.126` |

---

## VLAN 30 — Sales

**Network Details:**
- Subnet: `10.0.0.128/26`
- Subnet Mask: `255.255.255.192`
- Default Gateway: `10.0.0.190`

| Device | IPv4 Address | Subnet Mask | Default Gateway |
|---------|---------------|--------------|------------------|
| PC5 | `10.0.0.129` | `255.255.255.192` | `10.0.0.190` |
| PC6 | `10.0.0.130` | `255.255.255.192` | `10.0.0.190` |

---

**To configure the PCs default gateway**: 
- Click on the PC
- Click on Config
- Enter the default gateway

**To configure IP addresses for the PCs**:
- Click on the PC & Desktop
- Click IP configuration
- Click Static
- Enter the IP and Subnet Mask

---

## Notes

- Each VLAN is assigned to a unique `/26` subnet, supporting up to **62 usable hosts**.
- I used the last IP for each subnet as the default gateway
