# Task 2:  Configure Layer 2 EtherChannel with PAgP (ASW2 & DSW2)

In this task, I will:

- Create a **Layer 2 EtherChannel** between **ASW2** and **DSW2** using **Port Aggregation Protocol (PAgP)**
- Configure the **Port-Channel** as a **trunk**

## Topology For Reference
<img width="642" height="355" alt="TFR" src="https://github.com/user-attachments/assets/5a76e157-717d-4b89-b10b-70e065bc93b8" />

These links will be bundled into **Port-Channel 1** on both switches.

**Note: ASW2 and DSW2 have the same speed, duplex and the default vlan (vlan 1)**

## Step 1️⃣ Configure PAgP EtherChannel on ASW2

#### 🔷 On ASW2 Enter global configuration mode:

```bash
enable
configure terminal
```

#### 🔷 Enter interface range for ASW2 G0/1 and G0/2:
```bash
interface range g0/1 - 2
```

#### 🔷 Enable PAgP and add them to channel-group 1 in desirable mode:
```bash
channel-group 1 mode desirable
```

**Expected Output ✅:**

<img width="906" height="213" alt="T2-ASW2-portchannel-created" src="https://github.com/user-attachments/assets/99917979-906c-4e51-a398-cc435502825c" />

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

### 🔶 Verify ASW2 PAgP EtherChannel 
```bash
show etherchannel summary
```

**Expected Output ✅:**

<img width="823" height="347" alt="T2-ASW2-v-etherchannel" src="https://github.com/user-attachments/assets/c0d91f22-9386-4aea-921e-6d2ac60b1c31" />

