# 🛠️ Task 4 – Fix DHCP Snooping Option 82 Issue

## 📌 Objective
Fix the DHCP Snooping issue that prevents **PC1** from receiving an IP address.

In this lab, the DHCP request fails because **Option 82** (DHCP relay information) was added and the DHCP message that is why it got **dropped**.

✅ I will disable the DHCP Snooping information option and then retest DHCP.

---

## 🧠 Simple Explanation

- Some switches add **Option 82** to DHCP messages
- In this setup, that causes the DHCP message to be **dropped**
- The fix is to stop the switches from adding that option

## Topology For Reference

<img width="667" height="221" alt="topology" src="https://github.com/user-attachments/assets/0437e21d-9c1c-483d-b25a-dc0aa1e8f15a" />

---

## ⚙️ Fix Configuration (Run on SW1 and SW2)

### 1️⃣ Enter Global Configuration Mode

```bash
configure terminal
```

### 2️⃣ Disable the DHCP Snooping Information Option (Option 82)

```bash
no ip dhcp snooping information option
```

### 3️⃣ Exit

```bash
end
```

## ✅ Verification

### 🧪 Retest DHCP (PC1)

#### 1️⃣ On PC1, Renew the IP Address Again

```bash
ipconfig /renew
```

**✅ Expected Result**

<img width="570" height="236" alt="PC1-ipconfig-renew-good" src="https://github.com/user-attachments/assets/18cf4a16-5790-4719-b033-fb6fbcd3fabd" />




