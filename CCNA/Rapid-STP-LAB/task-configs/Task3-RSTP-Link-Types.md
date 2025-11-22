# Task 3 Configure RSTP Link Types 🔗

## Purpose of This Task 🎯
- Configure the correct RSTP link type on each interface.  
- Understand the difference between shared, point-to-point, and edge links.  
- Identify how hubs affect link-type selection.
- Verify RSTP link types using the CLI.

## Topology For Reference:
<img width="679" height="427" alt="Topology" src="https://github.com/user-attachments/assets/eec8b2e8-5a63-4614-8f58-e55a9f4b7c18" />

### 🛠️ Step 1: Configure SW1

**Enter global configuration mode:**

```bash
enable
conf t
```

### 1️⃣ Configure F0/1 as point-to-point (connected to SW2)

```bash
interface f0/1
spanning-tree link-type point-to-point
exit
```

### 2️⃣ Configure F0/2 and F0/3 as shared (both connect to a hub)

```bash
interface range f0/2, f0/3
spanning-tree link-type shared
exit
```

### 3️⃣ Configure F0/24 as an edge port (PortFast)
```bash
int f0/24
spanning-tree portfast
exit
```

### 4️⃣ Verify

**command:**
```bash
show spaning-tree
```

**Expected output:✅**

<img width="685" height="416" alt="v-sw1" src="https://github.com/user-attachments/assets/3fab6e56-b169-4c18-bb17-0e9dfdb1203c" />

**Note on SW1 F0/24 is connected to a hub, On a real cisco switch it will display both edge and shared in the type section**
