# 📱 Task 4 Associate Wireless Client and Verify Connectivity

## 📌 Objective

Add a wireless client to the topology and verify that it can:

- Associate to an AP
- Authenticate using **WPA2-PSK**
- Receive an IP address via DHCP

## 🧠 Simple Explanation

After configuring the WLANs on the WLC, the final step is to prove everything works:

- Client connects to SSID (Internal or Guest)
- Client enters the WPA2 password
- Client receives an IP address

## Topology For Reference

<img width="491" height="251" alt="topology" src="https://github.com/user-attachments/assets/72d0bdd5-e278-4cca-9727-160600a81eb2" />

---

## 🧪 Part A - Add a Wireless Client (Smartphone)

### 1️⃣ Add a Smartphone to the Topology

- Drag a **Smartphone** into the topology

<img width="635" height="287" alt="add-smartphone" src="https://github.com/user-attachments/assets/19c54b89-c127-431d-931e-3109bee6ba04" />

### 2️⃣ Connect the Smartphone to the WLAN

- Click the Smartphone
- Clicn on **Config**
- Click on **Wireless0**

### 3️⃣  Enter wireless details

- For the SSID enter: **Internal**
- For the Authentication check **WPA2-PSK**
- For the PSK Pass Phrase enter: **ccnaccna**


<img width="703" height="370" alt="smarphone-connect" src="https://github.com/user-attachments/assets/ae2d05c9-386b-4d01-ab1c-5b680b620101" />

<img width="675" height="255" alt="smartphone-wifi" src="https://github.com/user-attachments/assets/a8a82b72-fa88-4ab0-bb47-d888458e8aec" />

The smartphone successfully connected to the WLAN.

<img width="479" height="127" alt="smartphone-ip" src="https://github.com/user-attachments/assets/ee7dfbe8-3a2a-4db3-8c6f-dc8d84a7955b" />

Note: The smartphone received an IP from the wrong DHCP pool (Management Pool), Its suppose to recieve an IP addresses for the VLAN 100 subnet see below.

<img width="397" height="63" alt="VLAN-DHCP" src="https://github.com/user-attachments/assets/cd79bd23-3dc7-4c9b-a2d9-024926be48cf" />
