# Task 5: Verify EtherChannel Load-Balancing Method

In this task, I will:

- Check the **current EtherChannel load-balancing method** on each switch  
- Confirm whether all switches use the **same default method** ✅

## Topology For reference
<img width="576" height="295" alt="topology" src="https://github.com/user-attachments/assets/8197f895-46ff-43a6-9edd-6209fdf9ee68" />

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
**Note: In this lab, all switches use the same default EtherChannel load-balancing method: source MAC address.**

#### 2️⃣ show etherchannel load-balance on ASW2 output:

<img width="654" height="105" alt="T5-ASW2-lb" src="https://github.com/user-attachments/assets/8b2b18e1-251a-4b49-8601-b6bccd4ecd37" />

#### 3️⃣ show etherchannel load-balance on DSW1 output:

<img width="719" height="158" alt="T5-DSW1-lb" src="https://github.com/user-attachments/assets/0580cd08-1bac-4fa4-aa93-2b58fd85b87b" />

#### 4️⃣ show etherchannel load-balance on DSW2 output:

<img width="602" height="157" alt="T5-DSW2-lb" src="https://github.com/user-attachments/assets/e74e6787-c0f3-4503-b7c6-4ea8ed9612bb" />

## 5️⃣ Summary Table

| Switch | Command                        | Default Load-Balancing Method |
|--------|--------------------------------|--------------------------------|
| ASW1   | `show etherchannel load-balance` | Source MAC address            |
| DSW1   | `show etherchannel load-balance` | Source MAC address            |
| ASW2   | `show etherchannel load-balance` | Source MAC address            |
| DSW2   | `show etherchannel load-balance` | Source MAC address            |

