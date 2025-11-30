# Task 3: Configure Layer 3 Static EtherChannel (DSW1 & DSW2)

In this task, I will:
- Configure a **Layer 3 EtherChannel** between **DSW1** and **DSW2**
- Use **static EtherChannel (mode on)**  
- Remove switchport mode and make the Port-Channel a **Layer 3 interface**
- Assign **IP addresses** to the Port-Channel
- Verify the EtherChannel

## Topology For Reference
<img width="638" height="364" alt="TFR" src="https://github.com/user-attachments/assets/fa099520-20d5-48c4-a082-efb19ec0c601" />

These links will be bundled into **Port-Channel 1** on both switches.

#### Note: DSW1 and DSW2 have the same speed, duplex and the default vlan (vlan 1)

## 1️⃣ Configure Static EtherChannel on DSW2

#### 🔷 Enter global configuration mode:

```bash
enable
conf t
```

#### 🔷 Go into the interface range for G1/0/1 and G1/0/2:
```bash
interface range g1/0/1 - 2

```

#### 🔷 Configure static EtherChannel using mode on and put them in channel-group 2:
```bash
channel-group 2 mode on
```

**Expected Output ✅:**

<img width="759" height="162" alt="T3-DSW2-L3-PC-created" src="https://github.com/user-attachments/assets/7be2f598-a6ba-4c91-956b-b43ce5798f1c" />

```bash
exit
```

#### 🔷 Go into the new Port-Channel 2 interface:

```bash
interface port-channel 2
```

#### 🔷 Make it a layer 3 port:

```bash
no switchport
```

**Expected Output ✅:**

<img width="840" height="151" alt="T3-DSW2-pc2-up" src="https://github.com/user-attachments/assets/8ef03b0b-92d3-4854-a476-3d80fd04ebeb" />

**Note:** Port channel 2 on DSW2 interface state is now up


#### 🔷 Assign the IP address to Port-Channel 2:
```bash
ip address 10.0.0.2 255.255.255.252
```

**Exit to privileged EXEC mode:**
```bash
end
```

#### 🔍 Verify on DSW2:

```bash
show ip interface brief
```

**Expected Output ✅:**

<img width="815" height="170" alt="T3-DSW2-show-ip-int-brief" src="https://github.com/user-attachments/assets/f82fccfa-a96d-4de8-9178-f70219b9bea1" />

```bash
show etherchannel summary
```

**Expected Output ✅:**

<img width="644" height="369" alt="T3-DSW2-verify-etherchannel" src="https://github.com/user-attachments/assets/4da14ffd-6103-4dfa-acc6-a2edb34136d9" />


## 2️⃣ Configure Static EtherChannel on DSW1

#### 🔷 Enter global configuration mode:

```bash
enable
conf t
```

#### 🔷 Go into the interface range for G1/0/1 and G1/0/2:
```bash
interface range g1/0/1 - 2

```

#### 🔷 Configure static EtherChannel using mode on and put them in channel-group 2:
```bash
channel-group 2 mode on
```

**Expected Output ✅:**

<img width="832" height="144" alt="T3-DSW1-pc-created" src="https://github.com/user-attachments/assets/f1ef6d59-721f-45a5-b9f7-884c561cf53e" />

```bash
exit
```

#### 🔷 Go into the new Port-Channel 2 interface:

```bash
interface port-channel 2
```

#### 🔷 Make it a layer 3 port:

```bash
no switchport
```

**Expected Output ✅:**

<img width="853" height="113" alt="T3-DSW1-pc2-up" src="https://github.com/user-attachments/assets/1113b3b9-51f0-46e0-b035-893169f98e03" />

**Note:** Port channel 2 on DSW1 interface state is now up

#### 🔷 Assign the IP address to Port-Channel 2:
```bash
ip address 10.0.0.1 255.255.255.252
```

**Exit to privileged EXEC mode:**
```bash
end
```

#### 🔍 Verify on DSW1:

```bash
show ip interface brief
```

**Expected Output ✅:**

<img width="828" height="151" alt="T3-DSW1-show-ip-int-brief" src="https://github.com/user-attachments/assets/188a94d0-f0ef-448b-88ed-e0406d5950dd" />

```bash
show etherchannel summary
```

**Expected Output ✅:**

<img width="748" height="370" alt="T3-DSW1-verify-etherchannel" src="https://github.com/user-attachments/assets/5bf45522-3892-4a9a-8709-2c51d2c23808" />

