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

## 🧪 Part A – Trigger a Violation on SW1 (Shutdown Mode)

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



















