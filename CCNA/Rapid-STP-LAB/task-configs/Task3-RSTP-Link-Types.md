# Task 3 Configure RSTP Link Types 🔗

## Purpose of This Task 🎯
- Configure the correct RSTP link type on each interface.  
- Understand the difference between shared, point-to-point, and edge links.  
- Identify how hubs affect link-type selection.
- Verify RSTP link types using the CLI.

## Topology For Reference:
<img width="679" height="427" alt="Topology" src="https://github.com/user-attachments/assets/eec8b2e8-5a63-4614-8f58-e55a9f4b7c18" />

## 🛠️ Step 1: Configure SW1

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
show spanning-tree
```

<br/>

**Expected output:✅**

<img width="685" height="416" alt="v-sw1" src="https://github.com/user-attachments/assets/3fab6e56-b169-4c18-bb17-0e9dfdb1203c" />

**Note SW1 F0/24 is connected to a hub, On a real cisco switch it will display both edge and shared in the type section**


## 🛠️ Step 2: Configure SW2

### Enter global configuration mode:

```bash
enable
conf t
```

### 1️⃣ Configure F0/1, F0/2, G0/1 as point-to-point

```bash
interface range f0/1, f0/2, g0/1
spanning-tree link-type point-to-point
exit
```

### 2️⃣ Configure F0/23 and F0/24 as edge ports

```bash
interface range f0/23, f0/24
spanning-tree portfast
exit
```

### 3️⃣ Verify

**command:**
```bash
show spanning-tree
```

**Expected output:✅**

<img width="687" height="458" alt="v-sw2" src="https://github.com/user-attachments/assets/db0ca6b5-9875-4202-8888-d3a16514fe73" />

**Note: Edge ports connected to end hosts will be point to point links if they are using full duplex, thats why f0/23 and f0/24 shows p2p under the type column**


## 🛠️ Step 3: Configure SW3

### Enter global configuration mode:

```bash
enable
conf t
```

### 1️⃣ Configure F0/2 as shared (connected to Hub1)

```bash
interface f0/2
spanning-tree link-type shared
exit
```

### 2️⃣ Configure F0/1 and G0/1 as point-to-point

```bash
interface range f0/1, g0/1
spanning-tree link-type point-to-point
exit
```

### 3️⃣ Configure F0/24 as an edge port (PortFast)

```bash
interface f0/24
spanning-tree portfast
exit
```

4️⃣ Verify

**command:**
```bash
show spanning-tree
```

**Expected output:✅**

<img width="668" height="436" alt="v-sw3" src="https://github.com/user-attachments/assets/0016f296-b2fd-41cd-abc0-55677947943a" />


## 🛠️ Step 4: Configure SW4

### Enter global configuration mode:

```bash
enable
conf t
```

### 1️⃣ Configure F0/1 and F0/2 as point-to-point 

```bash
interface range f0/1, f0/2
spanning-tree link-type shared
exit
```

### 2️⃣ Configure F0/24 as an edge port (PortFast)

```bash
interface f0/24
spanning-tree portfast
exit
```

### 3️⃣ Verify

**command:**
```bash
show spanning-tree
```

**Expected output:✅**

<img width="673" height="420" alt="v-sw4" src="https://github.com/user-attachments/assets/b088140f-3352-4488-b1f6-ad8925d5f549" />


## RSTP Link Types Explained 📘

- Point-to-Point → Full-duplex connection between two switches  
- Shared → Half-duplex connection (usually involving hubs)  
- Edge Port → Connected to an end device; enable PortFast  


## Important Notes ⚠️

- Edge + Point-to-Point can both exist on the same interface (real switches will show both when PortFast is enabled).
- Packet Tracer does not display both but real cisco IOS switches do.
- Shared = half-duplex (hub involved)
- Point-to-Point = full-duplex (switch-to-switch)  
