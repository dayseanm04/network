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

## 🧪 Simulation Steps

First ping PC2 from PC1 for the ARP process to complete

### 1️⃣ Switch to Simulation Mode

- At the bottom right, click **Simulation** (instead of Realtime)

---

### 2️⃣ Generate Data Traffic (Ping)

On **PC1**:
- Open **Desktop → Command Prompt**
- Run:
- 
```bash
ping 192.168.10.12
```

### 3️⃣ Inspect the First Frame
- In the event list, click the first ICMP frame
- Click Outbound PDU Details

<img width="931" height="260" alt="T3-PDU" src="https://github.com/user-attachments/assets/1ecc5bb6-fa2c-4f29-aeac-834fb75ecda6" />

Note: these no tpid 0x8100 whihc refers to 802.1Q VLAN tagging




