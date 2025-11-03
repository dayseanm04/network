# 🧱 Task 1: Finding the Root Bridge

## Topology For Reference
<img width="758" height="349" alt="Topology" src="https://github.com/user-attachments/assets/6e395411-796c-4456-86e3-87b9cc7f3e44" />

## 🎯 Objective
Determine which switch becomes the **Root Bridge** in the Spanning Tree Protocol (STP) topology by analyzing each switch’s **Bridge ID (BID)** , which consists of the **Bridge Priority** and the **MAC address**.

---

## 📊 Switch Information

| **Switch** | **Priority** | **MAC Address** | **Bridge ID (BID)** |
|-------------|---------------|------------------|----------------------|
| SW1 | 32769 | 0001.4338.79D8 | 32769.0001.4338.79D8 |
| SW2 | 28673 | 0002.16D6.D0B8 | 28673.0002.16D6.D0B8 |
| SW3 | 24577 | 00E0.F9E6.44A5 | 24577.00E0.F9E6.44A5 |
| SW4 | 32769 | 0090.0C01.9587 | 32769.0090.0C01.9587 |

---

## 🔍 Process
STP elects the **Root Bridge** by comparing the **Bridge ID** of all switches in the network.

The **Bridge ID (BID)** = **Bridge Priority** + **MAC Address**

1. The switch with the **lowest Bridge Priority** becomes the Root Bridge.  
2. If there is a **tie in priority**, the switch with the **lowest MAC address** wins.  

---

## 🧠 Analysis
- **SW3** has the **lowest Bridge Priority (24577)** among all switches.  
- Therefore, **SW3** becomes the **Root Bridge**.  

✅ **Result:**  
 **SW3 is the Root Bridge** because it has the lowest Bridge Priority value (**24577**).  

---

## 🌐 Root Bridge Characteristics
- All ports on the **Root Bridge** automatically become **Designated Ports (DP)**.  
- These ports will remain in the **Forwarding state**.  
- The **Root Bridge** has a **Root Path Cost of 0** because it is the root of the STP topology.  
