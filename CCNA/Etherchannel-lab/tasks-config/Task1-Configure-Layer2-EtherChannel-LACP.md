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

#### 🔷 Check the VLANs on ASW1:

```enable
show vlan brief
```

**Expected Output ✅:**

<img width="810" height="273" alt="T1-ASW1-show-vlan-brief" src="https://github.com/user-attachments/assets/5b4ae2e7-d040-4c42-a08f-066b7913ea78" />

**Note: There is only the default VLAN on ASW1 (VLAN 1)**

#### 🔷 Check trunk status (there should be no trunk yet):

```bash
show interface trunk
```

**Expected Output ✅:**

<img width="567" height="56" alt="T1-ASW1-trunk-dont-show" src="https://github.com/user-attachments/assets/4115d1fc-6bcf-4b05-b925-adae525ec7cc" />


## 2️⃣ Verify Interfaces on DSW1

#### 🔷 On **DSW1** and enter privileged EXEC mode:

```bash
enable
```

#### 🔷 Check speed and duplex of G1/0/3 and G1/0/4:

```bash
show interfaces status
```

**Expected Output ✅:**

<img width="812" height="555" alt="T1-DSW1-show-int-status" src="https://github.com/user-attachments/assets/a9a2ba9a-f9c5-43b6-86da-8125a80d131d" />

#### 🔷 Check the VLANs on DSW1:

```enable
show vlan brief
```

**Expected Output ✅:**

<img width="929" height="230" alt="T1-DSW1-show-vlan-brief" src="https://github.com/user-attachments/assets/bd995166-8c55-413b-b3de-d9357a65c220" />

#### 🔷 Check trunk status (there should be no trunk yet):

```bash
show interface trunk
```

<img width="445" height="58" alt="T1-DSW1-show-int-trunk" src="https://github.com/user-attachments/assets/8feeaba3-3d25-41ae-a427-936adf7fe140" />

## 3️⃣ Configure LACP EtherChannel on ASW1

Now I will bundle G0/1 and G0/2 into Port-Channel 1 using LACP and configure it as trunk.

#### 🔷 Enter interface range for ASW1 G0/1 and G0/2:
```bash
interface range 0/1 - 2
```

#### 🔷 Enable LACP and assign them to channel-group 1 in active mode:

```bash
channel-group 1 mode active
```

**Expected Output ✅:**

<img width="906" height="222" alt="T1-ASW1-port-channel-created" src="https://github.com/user-attachments/assets/37113864-8435-414f-8bd0-69250aa6f5ac" />

```bash
exit
```

#### 🔷 Go into the new Port-Channel interface:

```bash
interface port-channel 1
exit
```

#### 🔷Set the Port-Channel as a trunk:
```bash
switchport mode trunk
end
```

### 🔶 Verify the LACP EtherChannel & Trunk on ASW1

```bash
show interfaces status
```

**Expected Output ✅:**

<img width="823" height="151" alt="T1-ASW1-verify-Port-channel" src="https://github.com/user-attachments/assets/bdd9c223-3975-4bcf-ae8a-e86d16955629" />

<br/>

```bash
show run
```

**Expected Output ✅:**

<img width="485" height="77" alt="T1-ASW1-show-run1" src="https://github.com/user-attachments/assets/0653b040-cd37-4e9b-a7df-104c75b1a3e9" />

<img width="507" height="173" alt="T1-ASW1-show-run2" src="https://github.com/user-attachments/assets/f3fd2802-3ec6-4a7d-ab35-e5cbf8e1183a" />


### 🔶 Verify etherchannel
```bash
show etherchannel summary
```

**Expected Output ✅:**

<img width="832" height="337" alt="T1-ASW1-v-etherchannel" src="https://github.com/user-attachments/assets/7538adb6-86f2-41af-b7cb-cd1d4fc56e58" />

**Note: Port-channel 1 is Down and the G0/1 and G0/2 interface has the I flag because DSW1 is not configured yet.**

## 4️⃣ Configure LACP EtherChannel on DSW1

#### 🔷 Enter interface range for G1/0/3 and G1/0/4:
```bash
interface range g/0/3 - 4
```

#### 🔷 Enable LACP and assign them to channel-group 1 in active mode:
```bash
channel-group 1 mode active
```

**Expected Output ✅:**

<img width="925" height="292" alt="T1-DSW1-Port-channel-created" src="https://github.com/user-attachments/assets/9253c235-dfa5-4485-925d-409c32f76afa" />


```bash
exit
```

#### 🔷 Go into the new Port-Channel interface:

```bash
interface port-channel 1
exit
```

#### 🔷Set the Port-Channel as a trunk:
```bash
switchport mode trunk
end
```

**Note: On some switches they might be multiple trunk encapsulations you may need:**
```bash
switchport trunk encapsulation dot1q
```

### 🔶 Verify the LACP EtherChannel & Trunk on ASW1

```bash
show interfaces status
```

**Expected Output ✅:**

<img width="826" height="172" alt="T1-DSW1-show-int-stat" src="https://github.com/user-attachments/assets/9458832a-f38f-4f7f-a14b-a2802be75fbb" />

### 🔶 Verify etherchannel

```bash
show etherchannel summary
```

**Expected Output ✅:**

<img width="820" height="351" alt="T1-verify-DSW1-etherchannel" src="https://github.com/user-attachments/assets/0de5d7a9-5317-4ce2-bb8f-bdd48f1c6f6f" />


<br/>


#### 🔷 show spanning-tree on ASW1 and DSW1: shows the port channel not the individual ports because the ports are treated as 1 single port.

**ASW1 Expected Output ✅:**

<img width="821" height="362" alt="T1-ASW1-show-stp" src="https://github.com/user-attachments/assets/04dacecf-673d-413e-a8e0-b76169e1997e" />

**DSW1 Expected Output ✅:**
<img width="791" height="360" alt="T1-DSW1-show-stp" src="https://github.com/user-attachments/assets/99fde5ce-483b-425e-8c75-ede718bd2199" />


