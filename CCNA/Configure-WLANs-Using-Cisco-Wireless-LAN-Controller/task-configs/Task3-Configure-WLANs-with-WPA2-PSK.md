# 🔐 Task 3 Configure WLANs with WPA2 PSK

## 📌 Objective

Create and configure two WLANs on **WLC1**:
- 🏥 **Internal WLAN**
- 🧑‍⚕️ **Guest WLAN**

Each WLAN will be:

- Enabled on the WLC
- Mapped to the correct **dynamic interface**
- Secured using **WPA2-PSK**

## 🧠 Simple Explanation

On a Cisco 3504 Wireless Controller:

- A **WLAN** = the wireless network (SSID) users connect to
- The WLAN must be mapped to a **dynamic interface** (Internal or Guest)
- **WPA2-PSK** protects the WLAN using a shared password

## Topology For Reference

<img width="491" height="251" alt="topology" src="https://github.com/user-attachments/assets/72d0bdd5-e278-4cca-9727-160600a81eb2" />

---

## 📋 WLAN Plan (Fill In Your Values)

| WLAN | SSID | WLAN ID | Interface Mapping | Security |
|------|------|--------|------------------|----------|
| Internal | Internal | 1 | Internal | WPA2-PSK |
| Guest | Guest | 2 | Guest | WPA2-PSK |

📌 WLAN IDs must be **unique** on the WLC.

---

# ✅ Part A - Create the WLANs (WLC GUI)

## 1️⃣ Click on the WLANs tab

<img width="899" height="170" alt="WLAN-tab" src="https://github.com/user-attachments/assets/8e2dc235-ce70-48c2-a8ed-35be7f9933b5" />

## 2️⃣ Create the Internal WLAN

Click **Go** on the top right and enter:

- **Profile Name:** `Internal`
- **SSID:** `Internal`
- **WLAN ID:** `1`

Click **Apply**

<img width="766" height="239" alt="T4-1" src="https://github.com/user-attachments/assets/17437fb2-fac9-4741-8b35-e78c3baa8cf3" />

## 3️⃣ Enable the WLAN

Check the Enable checkbox

## 4️⃣ Map Internal WLAN to the Internal Interface

Click on the **Internal WLAN** ID number, then set:
- **Interface/Interface Group:** `Internal`

<img width="447" height="170" alt="Internal-group" src="https://github.com/user-attachments/assets/92c00ae2-22c0-4896-a4ee-97ba2d1c0105" />

Click **Apply** on the top right.

---

## 2️⃣ Create the Guest WLAN

Click **Go** on the top right and enter:

- **Profile Name:** `Guest`
- **SSID:** `Guest`
- **WLAN ID:** `2`

Click **Apply**

<img width="596" height="235" alt="T4-2" src="https://github.com/user-attachments/assets/14f11a62-0d4b-4ad1-95aa-35d818e69437" />



<img width="988" height="420" alt="T4-4" src="https://github.com/user-attachments/assets/247c5ca4-f3e1-4f9c-a6f6-e2c0ab312c06" />



