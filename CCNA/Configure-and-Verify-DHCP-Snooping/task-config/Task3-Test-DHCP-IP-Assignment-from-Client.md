# 🖥️ Task 3 – Test-DHCP-IP-Assignment-from-Client

## 📌 Objective

Test whether **PC1** can successfully receive an IP address from the DHCP server **after DHCP Snooping is enabled**.

I will run `ipconfig /renew` on PC1 and observe:

- ✅ Does PC1 get an IP address?
- ❓ If it fails, why does it fail?

## 🧠 Simple Explanation

DHCP Snooping blocks certain DHCP messages on **untrusted ports**.
If something is wrong, the switch may **drop the DHCP traffic**, causing the client to fail to get an IP address.

## Topology For Reference

<img width="667" height="221" alt="topology" src="https://github.com/user-attachments/assets/0437e21d-9c1c-483d-b25a-dc0aa1e8f15a" />

---

## 🧪 Steps (PC1)

### 1️⃣ Open PC1 Command Prompt

- Click **PC1**
- Go to **Desktop**
- Open **Command Prompt**

---

### 2️⃣ Renew the IP Address

Run:

```bash
ipconfig /renew
```

**✅Expected Output**

<img width="547" height="243" alt="PC1-ipconfig-renew" src="https://github.com/user-attachments/assets/159fdbbf-5aa2-4160-afd3-7bb1650abae4" />

### 2️⃣ Renew the IP Address in simulation moode:

```bash
ipconfig /renew
```

Click on the SW2 to SW1 PDU.  Look at the DHCP Client Identifier Option

<img width="726" height="261" alt="option-82-frame" src="https://github.com/user-attachments/assets/67e1d6ed-a1c6-45ca-98e5-47e6654f8bc8" />


### ❌ The request should fail at first.

#### ❓ Why it fails

- PC1 is on an untrusted port
- SW2 adds DHCP Option 82 information
- When the DHCP message is forwarded to **SW1**, **SW1** drops it because of the **Option 82** behavior in this setup

📌 This is the problem I will fix in Task 4.

