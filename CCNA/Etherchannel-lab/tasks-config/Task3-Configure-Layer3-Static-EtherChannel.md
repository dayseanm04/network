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

#### Make it a layer 3 port:

```bash
no switchport
```
