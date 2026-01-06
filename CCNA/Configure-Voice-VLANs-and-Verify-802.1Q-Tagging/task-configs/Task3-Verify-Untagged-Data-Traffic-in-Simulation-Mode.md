# 🖥️ Task 3 – Verify Untagged Data Traffic in Simulation Mode (PC1 ➜ PC2)

## 📌 Objective

Use **Packet Tracer Simulation Mode** to verify whether **data traffic** (PC-to-PC) is **tagged with a VLAN ID**.

✅ I will:

- Ping from **PC1 to PC2**
- Inspect the **Outbound PDU details**
- Answer: **Is the traffic tagged with a VLAN ID?**

## 🧠 What I am Testing 

Even though PCs are in **VLAN 10**, switches typically send **data frames untagged** on **access ports**.

📌 Expectation:

- **PC traffic = NOT tagged** (access port behavior)


## Topology For Reference

<img width="657" height="253" alt="topology" src="https://github.com/user-attachments/assets/3459f83e-c98d-4bca-826a-c8d8641898e7" />

---

## 🔎 Test Info

| Item | Value |
|------|-------|
| Data VLAN | VLAN 10 |
| PC1 IP (example) | 192.168.10.11 |
| PC2 IP (example) | 192.168.10.12 |
| Test | Ping PC2 from PC1 |

