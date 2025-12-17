# Task5 Test HSRP Preemption  🔄👑

## 🎯 Goal
Turn **R1** back on and observe whether it becomes the **active router** again (preemption behavior). 

## Toplogy For Reference

<img width="624" height="284" alt="toplogy" src="https://github.com/user-attachments/assets/0f9e5564-4206-43af-a79f-1afe60dc7aa1" />


## 🔌 Step-by-Step: Power On R1

### 1️⃣ Turn on R1

- Click **R1**
- Go to **Physical**
- Toggle the **power switch ON**

⏳ Wait a few seconds for the router to boot and for HSRP to update.

<img width="530" height="184" alt="R1-on" src="https://github.com/user-attachments/assets/84453e80-eb32-4bb1-ad27-77ac0f7aa6f3" />

## 🔍 Step-by-Step: Check HSRP State (R1 and R2)

### 2️⃣ On R1: Verify HSRP status

```bash
enable
show standby
```

**Expected Output✅:**

<img width="649" height="262" alt="T5-R1-is-active-Router" src="https://github.com/user-attachments/assets/abbb7435-6a0b-461e-9e97-a47bdc06e3be" />

**Note:** R1 is the Active Router again!

