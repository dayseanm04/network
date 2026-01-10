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

