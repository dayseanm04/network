# ⏰ Task 1 - Configure Software Clock (UTC)

## 🎯 Goal
Configure the **software clock** on **R1, R2, and R3** to:

- **Time:** `12:00:00`
- **Date:** `Dec 30 2020`
- **Timezone:** `UTC`


## Topology For Refernece

<img width="648" height="256" alt="topology" src="https://github.com/user-attachments/assets/e30bc4fe-1d0b-480f-82fd-509165d35916" />

---

## 🧩 Configure R1

### 1️⃣ Enter Privileged EXEC Mode (All Routers)

```bash
enable
```

### 2️⃣ Set the Software Clock (All Routers)

```bash
clock set 12:00:00 30 Dec 2020
```

### 3️⃣ Verify the Clock (All Routers)

**On R1 show clock**

**Expected output✅:**

<img width="466" height="77" alt="T1-R1-show-clock" src="https://github.com/user-attachments/assets/0585851c-c10f-4b1c-a2df-ccf8bd0b9a9e" />


**On R2 show clock**

**Expected output✅:**

<img width="423" height="80" alt="T1-R2-show-clock" src="https://github.com/user-attachments/assets/b39686e3-7f40-473a-a509-43f25f37854c" />

**On R3 show clock**

**Expected output✅:**

<img width="472" height="81" alt="T1-R3-show-clock" src="https://github.com/user-attachments/assets/690637b5-3c9c-44fa-b781-51bf89d369ed" />
