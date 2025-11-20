# Task 1: Identify the Root Bridge 🎛️

## Purpose of This Task 🎯
- Determine which switch becomes the Root Bridge.
- Examine port roles and states on the Root Bridge.
- Understand why hubs and collision domains change RSTP behavior.


## Topology For Reference:
<img width="679" height="427" alt="Topology" src="https://github.com/user-attachments/assets/eec8b2e8-5a63-4614-8f58-e55a9f4b7c18" />

<br/>

### SW1 is the Root Bridge because it has rthe lowest MAC address
- All switches shared have the same priority (32769).  
- SW1 had the lowest MAC address so it becomes the Root Bridge.  


## verify with the CLI

**In priviliged EXEC mode:**
```bash
show spanning-tree
```

**Expected Output ✅:**

<img width="788" height="362" alt="T1-SW1-root" src="https://github.com/user-attachments/assets/37eb5acd-e8ff-472f-b3f0-08c2205bd612" />

## Port Roles and States on SW1 (Root Bridge) 🔌
- F0/1  → Designated (Forwarding)  
- F0/2  → Designated (Forwarding)
- F0/24 → Designated (Forwarding)
- F0/3  → Backup (Discarding)

## Why Does SW2 have a backup port ⚠️

- SW1 has 2 interfaces connected into the **same collision domain**. **F0/2** and **F0/3** are both connect to a hub.
- RSTP allows **only one Designated Port per collision domain**. So RSTP must choose one with the lowest PortID
- STP port ID = the port priority + the port number.
- **SW1 F0/2** has the port id (128+2). - SW1 F0/3 has the port id (128+3).
- **SW1 F0/2** will become the degsnated port and F0/3 will be backup


