# 🧪 Task 4 – Simulation Mode: Ping youtube.com and Analyze DNS Traffic

## 🎯 Goal
Use **Simulation Mode** in Packet Tracer to observe what happens when **PC1 pings `youtube.com` by name**.


## Topology For Reference

<img width="626" height="254" alt="Topology" src="https://github.com/user-attachments/assets/7c66d56e-4913-4f1f-97fa-fa7b65588bf3" />

---

## ⚠️ IMPORTANT
🚨 **USE SIMULATION MODE FOR THIS STEP**


## ✅ Step-by-Step Instructions (Packet Tracer)

### 1️⃣ Switch Packet Tracer to Simulation Mode
- Click **Simulation** (bottom right in Packet Tracer)

✅ You should now see the event list and controls.

---

### 2️⃣ (Optional) Clear Old Events
To make results easier to read:
- Click **Reset Simulation** (or **Clear Event List**)

📌 This removes old packets from the list so you only see new traffic.

---

### 3️⃣ Open Command Prompt on PC1
- Click **PC1**
- Go to **Desktop**
- Click **Command Prompt**

---

### 4️⃣ Use the Simulation Mode

#### ♦️ On PC1, run:
- Click **Simulation**

---

### 5️⃣ Ping youtube.com by Name:
- `ping youtube.com`

**✅ Watch what appears in the event list.**

---

## 🔍 What You Should See (Packet Analysis)

### 🟦 DNS Query (PC1 ➜ DNS Server)

#### ✅ You should see a **DNS Query** sent first.  

This is PC1 asking: *“What is the IP address for youtube.com?”* (See Below)

<img width="1022" height="268" alt="DNS-Query" src="https://github.com/user-attachments/assets/c9cac704-3aba-4300-9e05-e7ceae0f3208" />


---

### 🟩 DNS Answer (DNS Server ➜ PC1)

#### ✅ You should then see a **DNS Answer** sent back.  

This response provides the IP address for youtube.com. (See Below)

<img width="1017" height="270" alt="DNS-Answer" src="https://github.com/user-attachments/assets/b075000d-cf21-4911-875f-017b876ff2d8" />

---

#### Note the Ping was successful

<img width="709" height="369" alt="T4-PC1-ping" src="https://github.com/user-attachments/assets/cdd68292-0b72-40cf-9dfc-e7dbe75c5532" />

