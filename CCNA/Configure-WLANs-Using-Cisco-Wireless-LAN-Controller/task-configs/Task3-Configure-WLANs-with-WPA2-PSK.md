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

