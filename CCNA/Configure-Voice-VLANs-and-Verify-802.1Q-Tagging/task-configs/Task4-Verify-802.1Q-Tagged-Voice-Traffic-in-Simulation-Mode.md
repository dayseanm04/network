# 📞 Task 4 – Verify 802.1Q-Tagged Voice Traffic in Simulation Mode (PH1 ➜ PH2)

## 📌 Objective

Use **Packet Tracer Simulation Mode** to verify whether **voice traffic** (IP phone call) is **tagged with a VLAN ID**.

✅ I will:

- Call from **PH1 to PH2**
- Inspect the **first voice-related frame**
- Confirm that the traffic is **802.1Q tagged** for the **Voice VLAN**

---

## 🧠 What I am Testing (Simple)

Voice VLANs are designed so the **phone sends tagged traffic**, even though it’s connected to an access port.

📌 Expectation:

- **Voice traffic = tagged (802.1Q / Dot1Q)**
- **VLAN ID = 20** (Voice VLAN)

## Topology For Reference

<img width="657" height="253" alt="topology" src="https://github.com/user-attachments/assets/3459f83e-c98d-4bca-826a-c8d8641898e7" />

---

## ☎️ Phone Info

| Device | Extension |
|--------|----------|
| PH1 | 2020 |
| PH2 | 2010 |

---

## 🧪 Simulation Steps

### 1️⃣ Switch to Simulation Mode

- At the bottom right, click **Simulation** (instead of Realtime)

---

### 2️⃣ Open PH1 Dial Pad

On **PH1**:
- Click the phone
- Go to the **GUI**
- Dial **2010** (PH2)

---

### 3️⃣ Watch the Packets Appear
- You should see call signaling traffic (often **SCCP** in Packet Tracer)
- Click the **first frame** generated for the call

<img width="825" height="149" alt="T4-call-" src="https://github.com/user-attachments/assets/fe635bb5-f747-4cf0-bc4a-9b80bcc5814b" />

---

