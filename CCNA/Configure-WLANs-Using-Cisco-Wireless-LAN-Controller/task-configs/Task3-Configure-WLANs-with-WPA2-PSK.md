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

<img width="994" height="425" alt="T4-3" src="https://github.com/user-attachments/assets/05e7eec4-b464-4727-a674-8304135908c1" />


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

## 3️⃣ Enable the WLAN

Check the Enable checkbox

<img width="988" height="420" alt="T4-4" src="https://github.com/user-attachments/assets/247c5ca4-f3e1-4f9c-a6f6-e2c0ab312c06" />

## 4️⃣ Map Guest WLAN to the Guest Interface

Click on the **Internal WLAN** ID number, then set:
- **Interface/Interface Group:** `Guest`

<img width="445" height="124" alt="Guest-group" src="https://github.com/user-attachments/assets/21a6c761-80c1-4f01-ad0d-a972d9a5170d" />

Click **Apply** on the top right.

# ✅ Part B - Configure WPA2-PSK Security for the WLANs

## 1️⃣ Set Security for Internal WLAN (WPA2-PSK)

Click **Internal WLAN** → **Security** tab:

- **Layer 2 Security:** `WPA + WPA2`
- **WPA+WPA2 Parameters:** `WPA2 Policy`
- **WPA2 Encryption:** AES
- **Authentication Key Management:** `PSK`
- **PSK Password:** `ccnaccna`

Click **Apply** on the top right.

<img width="754" height="659" alt="T5-1" src="https://github.com/user-attachments/assets/ad8de7ae-a490-4ad9-93ee-03a4ef374ef6" />

<img width="973" height="344" alt="T5-2" src="https://github.com/user-attachments/assets/fd581c73-91b5-444c-ae9c-3659ca9e4307" />

## 2️⃣ Set Security for Guest WLAN (WPA2-PSK)

Click **Internal WLAN** → **Security** tab:

- **Layer 2 Security:** `WPA + WPA2`
- **WPA+WPA2 Parameters:** `WPA2 Policy`
- **WPA2 Encryption:** AES
- **Authentication Key Management:** `PSK`
- **PSK Password:** `ccnaccna`

Click **Apply** on the top right.



