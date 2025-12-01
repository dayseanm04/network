# Task 5: Verify EtherChannel Load-Balancing Method

In this task, I will:

- Check the **current EtherChannel load-balancing method** on each switch  
- Confirm whether all switches use the **same default method** ✅

## 1️⃣ Check Load-Balancing on ASW1

#### ♦️ Enter privileged EXEC mode on **ASW1**:

```bash
enable
```

#### ♦️ Check the EtherChannel load-balancing method:
```bash
show etherchannel load-balance
```

**Expected Output ✅:**

<img width="625" height="112" alt="T5-ASW1-lb" src="https://github.com/user-attachments/assets/63cd3ddf-9890-4935-b6f3-62fbda53b8f7" />

<br/><br/>
**Note: all of the Switches uses Source MAC address as ther Etherchannel load balancing method**

