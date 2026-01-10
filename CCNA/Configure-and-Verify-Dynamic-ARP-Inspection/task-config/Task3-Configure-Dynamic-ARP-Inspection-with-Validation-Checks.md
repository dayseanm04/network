# 🛡️ Task3 Configure Dynamic ARP Inspection with Validation Checks

## 📌 Objective

Configure **Dynamic ARP Inspection (DAI)** on **SW1** and **SW2** to protect the network from: 

- 🛑 ARP spoofing
- 🛑 ARP poisoning

DAI will validate ARP packets using the **DHCP Snooping binding table** created in the previous task.

## 🧠 Simple Explanation

DAI checks ARP packets and only allows them if they look legitimate.

### ✅ DAI uses:

- **DHCP Snooping bindings** (IP ↔ MAC ↔ interface)

### ✅ I will also enable extra checks to strengthen security:

- Destination MAC validation
- Source MAC validation
- IP validation

## Topology For Reference

<img width="685" height="260" alt="topology" src="https://github.com/user-attachments/assets/6b428763-7bbc-4f14-aefa-c2624a090abc" />

---

## 📋 What I will Configure

On **SW1** and **SW2**:

- Enable DAI for **VLAN 1**
- Trust ports connected to a **router or switch**
- Enable ARP validation checks

---


## ⚙️ Configur2 – SW1

### 1️⃣ Enter Global Configuration Mode

```bash
enable
configure terminal
```

### 2️⃣ Enable DAI on VLAN 1

```bash
ip arp inspection vlan 1
```

### 3️⃣ Trust the Uplink Interface (Connected to SW2)

```bash
interface g0/1
ip arp inspection trust
exit
```

### 4️⃣ Enable Additional Validation Checks

```bash
ip arp inspection validate dst-mac ip src-mac
```

### 5️⃣ Exit

```bash
end
```


## ⚙️ Configure – SW2

### 1️⃣ Enter Global Configuration Mode

```bash
enable
configure terminal
```

### 2️⃣ Enable DAI on VLAN 1

```bash
ip arp inspection vlan 1
```

### 3️⃣ Trust the Uplink Interface (Connected to R1)

```bash
interface g0/2
ip arp inspection trust
exit
```

### 4️⃣ Enable Additional Validation Checks

```bash
ip arp inspection validate dst-mac ip src-mac
```

### 5️⃣ Exit

```1bash
end
```

## ✅ Verification

Run these commands on SW1 and SW2:

#### 🔷 On SW1 show ip arp inspection interfaces

<img width="732" height="531" alt="T3-SW1-show-ip-arp-inspec-int" src="https://github.com/user-attachments/assets/1d0cf718-8bd4-427e-8f5d-f581d6ca50e1" />

#### 🔷 On SW1 show ip arp inspection

<img width="758" height="187" alt="T3-SW1-show-ip-arp-inspect" src="https://github.com/user-attachments/assets/9fe706c5-4be4-4789-aca3-ac48afa8a67e" />


#### 🔷 On SW2 show ip arp inspection interfaces

<img width="671" height="533" alt="T3-SW2-show-ip-arp-inspec-int" src="https://github.com/user-attachments/assets/82a13cd4-9840-45e7-ad2c-33a4e8d8c3e9" />


#### 🔷 On SW2 show ip arp inspection

<img width="741" height="183" alt="T3-SW2-show-ip-arp-inspect" src="https://github.com/user-attachments/assets/bb697cae-eee5-4d11-8141-6d94d3b8d633" />

## Quick Test (Client Connectivity)

#### 🔷 On PC1 ipconfig /renew

<img width="599" height="307" alt="PC1-DHCP" src="https://github.com/user-attachments/assets/d9c5d15e-ee99-4774-b3de-ee1348a97265" />

PC1 successfuly received an IP Address from R1


















