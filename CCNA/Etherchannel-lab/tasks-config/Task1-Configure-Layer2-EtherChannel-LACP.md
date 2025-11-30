# Task 1: Configure Layer 2 EtherChannel with LACP (ASW1 & DSW1)

In this task, I:

- Checked interface status on **ASW1** and **DSW1**
- Configured a **Layer 2 EtherChannel** using **LACP (mode active)**
- Configured the **Port-Channel** as a **trunk**

## Topology For Reference
<img width="663" height="393" alt="TFR" src="https://github.com/user-attachments/assets/9ded89c2-e858-4d02-940e-6d17f357178d" />

These two links will be bundled into **Port-Channel 1** on both switches.

<br/>

**Note**: To configure EtherChannel the switches must have the same speed, duplex, switchport (access or trunk), If they are a trunk, they must have the same allowed VLANs and native VLANs.

## Step 1️⃣ Verify Interfaces on ASW1

#### 🔷 On **ASW1** and enter privileged EXEC mode:

```bash
enable
```

#### 🔷 Check speed and duplex of G0/1 and G0/2:

```bash
show interfaces status
```

**Expected Output ✅:**
<img width="826" height="522" alt="T1-ASW1-show-int-status" src="https://github.com/user-attachments/assets/6732e6bc-3b7a-4a19-abe8-282731c09464" />

**Note: ASW1 G0/1 and G0/2 have the same speed and duplex.**

