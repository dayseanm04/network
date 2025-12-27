# 🌎 Task 2 - Configure Time Zone

## 🎯 Goal
Configure the **time zone** on **R1, R2, and R3** so the router clocks reflect the **local time zone** instead of UTC. In this case EST.  
This ensures logs and timestamps match real-world time.

## Topology For Refernece

<img width="648" height="256" alt="topology" src="https://github.com/user-attachments/assets/e30bc4fe-1d0b-480f-82fd-509165d35916" />

---

## 🧩Configure R1, R2, and R3

### 1️⃣ Enter Configuration Mode (All Routers)

```bash
enable
configure terminal
```

### 2️⃣ Configure the Time Zone (All Routers)

```bash
clock timezone EST -5
```

**ℹ️ Adjust the time zone name and UTC offset if you are in a different region. In this lab I used New york EST (UTC -5)**

### 3️⃣ Verify the Time Zone Configuration (All Routers)

**On R1 show clock**

**Expected output✅:**

<img width="455" height="80" alt="T2-R1-show-clock" src="https://github.com/user-attachments/assets/e4429ad3-475e-4431-9dae-783d8f0a14fc" />

**On R2 show clock**

**Expected output✅:**

<img width="443" height="81" alt="T2-R2-show-clock" src="https://github.com/user-attachments/assets/7c034fb5-b765-4307-9086-79b52d32e737" />


**On R3 show clock**

**Expected output✅:**

<img width="455" height="82" alt="T2-R3-show-clock" src="https://github.com/user-attachments/assets/c906753d-f7d5-441a-95b2-7ffd29a85158" />


