# 🔧 Task 2 Configure Internal and Guest Dynamic Interfaces

## 📌 Objective

Create **dynamic interfaces** on **WLC1** for:
-  **Internal WLAN**
- **Guest WLAN**

## 🧠 Simple Explanation

On a Cisco WLC:
- A **WLAN (SSID)** must be mapped to an **interface**
- A **dynamic interface** represents a VLAN/subnet (ex: Internal vs Guest)
- When a client connects to an SSID, the WLC places the client into the **VLAN/subnet** linked to that interface

## Topology For Reference

<img width="491" height="251" alt="topology" src="https://github.com/user-attachments/assets/72d0bdd5-e278-4cca-9727-160600a81eb2" />

---

## 📋 Interface Plan 

| Interface | VLAN ID | IP Address | Subnet Mask | Default Gateway | DHCP Server |
|----------|---------|------------|-------------|-----------------|------------|
| Internal | 100 | 10.0.0.10 | 255.255.255.0 | 10.0.0.1 | 10.0.0.1 |
| Guest | 200 | 10.1.0.10 | 255.255.255.0 | 10.1.0.1 | 10.1.0.1 |

# ✅ Step by Step (WLC GUI)

## 🟢 Part A Create the interface

### 1️⃣ Go to the Interfaces Section

In the WLC GUI, navigate to:
- **Controller** → **Interfaces**

<img width="607" height="311" alt="T2-1" src="https://github.com/user-attachments/assets/37c27730-f7d2-4a48-8eff-3f12c33f6792" />

---

## 2️⃣ Create the Internal Dynamic Interface

Click **New** on the top right and enter the interface details.

<img width="606" height="180" alt="T3-2" src="https://github.com/user-attachments/assets/5957eb79-ee65-4fc4-bfe0-81edb20b332f" />

Interfance name: Internal, VLAN ID: 100 then click Apply then click Back

## 3️⃣ Create the Guest Dynamic Interface

Click **New** on the top right and enter the interface details.

<img width="608" height="160" alt="T3-3" src="https://github.com/user-attachments/assets/ffde18f7-d7e7-45ed-826b-c021c58fe933" />

Interfance name: Guest, VLAN ID: 200 then click Apply then click Back

### ✅ Results 

<img width="990" height="293" alt="T3-4" src="https://github.com/user-attachments/assets/ac706ac5-130f-4ecf-92ed-c2b45b4e5a62" />

## 🟢 Part B Configure the interfaces

### 1️⃣ Click on Internal 

<img width="823" height="300" alt="T3-5" src="https://github.com/user-attachments/assets/82455cea-854f-4ef8-81d7-cfa49d8bf549" />

Set the Port Number to 1 under the Physical Information section
Note: Port 1 is connected to the Switch. Give the Internal internal an IP addresss, Subnet Mask, Default Gateway and the DHCP Server. Note the default gateway and the DHCP Server is the SVI of VLAN 100. See bellow:

<img width="557" height="245" alt="show-run" src="https://github.com/user-attachments/assets/ef4f1264-a6f7-4764-b440-653903904b36" />

Click Apply on the Top right and go back and dont forget to Click save config on the top right, see bellow:

<img width="186" height="30" alt="image" src="https://github.com/user-attachments/assets/458265ab-a625-4f9a-bc4e-9ecbfbdb8150" />


### 2️⃣ Click on Guest 

<img width="788" height="305" alt="T3-6" src="https://github.com/user-attachments/assets/f675f57f-2b8c-4274-a497-7482a74331cb" />

Set the Port Number to 1 under the Physical Information section
Note: Port 1 is connected to the Switch. Give the Internal internal an IP addresss, Subnet Mask, Default Gateway and the DHCP Server. Note the default gateway and the DHCP Server is the SVI of VLAN 300.

Click Apply on the Top right and go back and dont forget to Click save config on the top right.

