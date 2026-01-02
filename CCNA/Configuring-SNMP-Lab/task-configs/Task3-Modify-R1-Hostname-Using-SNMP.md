# ✏️ Task 3 – Use SNMP Set to Change the Hostname of R1

## 🎯 Goal
Use **SNMP Set** message from **PC1** to **change the hostname of R1**.

This task demonstrates **SNMP management**, not just monitoring. You will use the **read/write SNMP community** to modify a router setting and then verify the change.

## Topology For Reference

<img width="333" height="135" alt="Topology" src="https://github.com/user-attachments/assets/cb46b216-b82f-4c84-8a90-aabeda8c2800" />

---

### 1️⃣ Open the MIB Browser on PC1

- Click **PC1**
- Go to **Desktop**
- Open **MIB Browser**

### 2️⃣ This was if you did this in task 2 no need to do this part again!

In the MIB Browser settings:
- Set the **Target IP** to **R1’s IP address**
- Set the **Read Community** to: `Cisco1`
- Set the **Write Community** to: `Cisco2`
- Make sure the operation is **GET**

<img width="385" height="229" alt="T2-MIB-info" src="https://github.com/user-attachments/assets/885d26c7-2f65-4451-8b55-00d929009d37" />

### 3️⃣ Select the Hostname Object (sysName)
Locate the **sysName** object in the MIB tree. See Below

<img width="406" height="436" alt="T2" src="https://github.com/user-attachments/assets/1261438c-9e1c-41e4-8a08-78fd417c00c5" />


### 4️⃣ Set a New Hostname

Under **SNMP MIBs** click MIB Tree all the way till you reach **.system** and click **.sysUpTime**. See Below

- Enter a **new hostname value** (example: `R2`)
- Make sure the operation is set to **SET**.

See below

<img width="764" height="293" alt="T3-1" src="https://github.com/user-attachments/assets/775fe583-a705-4afb-a654-03b43a4ebf43" />

**✅ Send the SNMP Set request**

---


## 🔍 Verification (R1)

### 5️⃣ Verify Hostname Change on R1

#### ♦️ On R1 show run | include hostname

<img width="605" height="176" alt="T3-4" src="https://github.com/user-attachments/assets/eed3bb29-df35-4b90-963c-983f29eef4e8" />
