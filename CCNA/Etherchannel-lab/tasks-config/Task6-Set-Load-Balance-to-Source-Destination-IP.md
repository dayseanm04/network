# Task 6: Configure Load Balancing to Source & Destination IP

In this task, I will:

- Change the **EtherChannel load-balancing method** on **all switches**
- Use **source and destination IP addresses** for better traffic distribution
- Verify the new configuration with `show etherchannel load-balance` ✅

## Topology For reference
<img width="576" height="295" alt="topology" src="https://github.com/user-attachments/assets/8197f895-46ff-43a6-9edd-6209fdf9ee68" />

## 1️⃣ Enter Global Configuration on Each Switch

Repeat these steps on **ASW1, ASW2, DSW1, and DSW2**.

#### 🔷 Enter privileged EXEC mode:

```bash
enable
configure terminal
```

## 2️⃣ Set Load Balancing to Source & Destination IP
```bash
port-channel load-balance src-dst-ip
end
```

## 3️⃣ Verify on All Switches
```
show etherchannel load-balance
```

**Expected Output ✅:**

<img width="648" height="161" alt="T6-verify-DSW2-load-balance" src="https://github.com/user-attachments/assets/80da4cc3-8d2a-4815-8879-70bb51f4169b" />


## 4️⃣ Quick Summary Table

| Switch | Verification Command              | Load-Balancing Method   |
|--------|-----------------------------------|--------------------------|
| ASW1   | `show etherchannel load-balance`  | src-dst-ip               |
| ASW2   | `show etherchannel load-balance`  | src-dst-ip               |
| DSW1   | `show etherchannel load-balance`  | src-dst-ip               |
| DSW2   | `show etherchannel load-balance`  | src-dst-ip               |
