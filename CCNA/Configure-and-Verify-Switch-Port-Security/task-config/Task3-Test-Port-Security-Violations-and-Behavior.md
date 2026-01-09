# 🚨 Task 2 – Trigger-and-Analyze-Port-Security-Violations

## 📌 Objective

Intentionally trigger **port security violations** on:
- **SW1 (Shutdown mode)** → port should go **down / err-disabled**
- **SW2 (Restrict mode)** → port should stay **up**, but violations are **counted** and traffic is **dropped**

I will observe and compare how each switch responds.

## 🧠 What I am Testing (Simple)

Port security can react differently depending on the **violation mode**:

| Switch | Interface(s) | Violation Mode | Expected Result |
|--------|--------------|----------------|-----------------|
| SW1 | F0/1–F0/3 | Shutdown | Interface goes **err-disabled** |
| SW2 | G0/1 | Restrict | Interface stays **up**, violations are **counted** |

## Topology For Reference

<img width="589" height="226" alt="topology" src="https://github.com/user-attachments/assets/f75f290f-5b2f-41a0-9526-3651fbaddc79" />

---

## 🧪 Part A – Trigger a Violation on SW2 (Restrict Mode)

### 1️⃣ Generate Normal Traffic First

From PC1/PC2/PC3, ping the default gateway to generate ARP entries:

```bash
ping 10.0.0.254
```

### 2️⃣ Add a New Test PC (Example: Test1)

- Connect Test1 to SW1 F0/1 (or any secured port)
- Click on Config
- Select FastEthernet and change the MAC address to example: 0011.0011.0011
- Cpnfigure IP
-   IP: 10.0.0.10
-   Mask: 255.255.255.0
-   Gateway: 10.0.0.254

## Reference Test1

<img width="599" height="322" alt="T2-Test1-diagram" src="https://github.com/user-attachments/assets/dad26435-2038-4001-bed4-b689434b6010" />


### 3️⃣ Trigger the Violation

On Test1, ping the gateway:

```bash
ping 10.0.0.254
```

## 🔎 Verify SW2 Violation

```bash
show port-security
```

<img width="744" height="136" alt="T2-SW2-show-port-sec" src="https://github.com/user-attachments/assets/04b53857-c1d4-4a47-a15b-bdb371150dbb" />

```bash
show port-security interface g0/1
```

<img width="642" height="251" alt="T2-SW2-show-port-sec-int" src="https://github.com/user-attachments/assets/1743689e-ca78-47b2-902a-5d4d5eeff347" />

## 🧪 Part B – Trigger a Violation on SW1 (Shutdown Mode)

### 1️⃣ Trigger a violation by connecting a MAC Address Event

### 2️⃣ Using the same New Test PC (Example: Test1)

- Connect Test1 to SW1 F0/1 (or any secured port)
- Click on Config
- Select FastEthernet and change the MAC address to example: 0011.0011.0011
- Cpnfigure IP
-   IP: 10.0.0.10
-   Mask: 255.255.255.0
-   Gateway: 10.0.0.254

## Reference Topology

<img width="515" height="230" alt="T2-SW1-F01-down" src="https://github.com/user-attachments/assets/da9f8186-1d27-4cac-8c0a-c65d710c3097" />

**Note:** The link lights turn red.

On **Test1**, ping the gateway:

```bash
ping 10.0.0.254
```

<img width="680" height="371" alt="T2-Test-PC-ping-failed" src="https://github.com/user-attachments/assets/06746cd6-2ab5-4ba0-b416-b29e59a38195" />

**Note:** The ping failed.

On **SW1** an F0/1 is adminstratively down log is displayed

<img width="826" height="158" alt="T2-SW1-log" src="https://github.com/user-attachments/assets/33e60776-41d3-47eb-b465-b10715961e7a" />

### On SW1 show port-security

<img width="734" height="172" alt="T2-SW1-show-pc-after-PC1-mac-change" src="https://github.com/user-attachments/assets/7963ce00-fae7-43d0-8a9c-37ad34e8ac00" />

### On SW1 show port-security interface F0/1

<img width="551" height="243" alt="T2-show-ps-int" src="https://github.com/user-attachments/assets/357b97c3-4756-4799-9f1c-f217f0788deb" />

### On SW1 show ip int brief

<img width="822" height="119" alt="SW1-show-int-stat" src="https://github.com/user-attachments/assets/42a4fd75-2305-4d41-abed-a191e06794be" />

Interface F0/1 is error disabled!
