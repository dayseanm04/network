# DTP & VTP Lab. Task1

# 🎯 Objective

Configure the switchports that connect the switches as **trunk ports**, **disable DTP** on those ports, and **verify** the administrative & operational mode of each interface.

**Switch connections**
- SW1 `G0/1` <--> SW2 `G0/1`  
- SW2 `G0/2` <--> SW3 `G0/1`

---

## Topology For Reference
<img width="642" height="304" alt="Topology" src="https://github.com/user-attachments/assets/2c7ec9fb-46be-43c9-9715-8c7ff7954117" />

<br>
<br>

# 🧩 SW1: Configure G0/1 as trunk & disable DTP

<br>

## 1️⃣ Enter global configuration mode:
```bash
enable
configure terminal
```

## 2️⃣ Enter interface configuration for G0/1 and configure as trunk:
```bash
interface G0/1
switchport mode trunk
```

**Note**: some switches support both dot1q and cisco ISL in that case you have to specify the encapsulation type with example: `switchport trunk encapsulation dot1q` before using the `switchport mode trunk` command.

<br>

## 3️⃣ Disable DTP on the interface:
```bash
switchport nonegotiate
```

## 4️⃣ Verify administrative and operational mode:
```bash
do show interfaces G0/1 switchport
```

**Expected output ✅:**

<img width="571" height="176" alt="T1-show-sp-g01-again" src="https://github.com/user-attachments/assets/9b3a5a5f-8111-4d62-a06a-44210b27b368" />


## 5️⃣ Check running-config

```bash
show run
```

**Expected output ✅:**

<img width="332" height="103" alt="T1-RC" src="https://github.com/user-attachments/assets/5d08c9f9-07fc-4d82-b78d-0e8f48b60e5d" />


## 6️⃣ save config 
```bash
write memory
```

<br>
<br>

# 🧩 SW2: Configure G0/1 & G0/2 as trunk & disable DTP

<br>

## 1️⃣ Enter global configuration mode:
```bash
enable
configure terminal
```

## 2️⃣ Configure both G0/1 and G0/2 as trunk ports (use interface range):

```bash
interface range G0/1 - 2
switchport mode trunk
```

**Expected output ✅:**

<img width="848" height="145" alt="T2-int-down-up" src="https://github.com/user-attachments/assets/1971f58b-497a-4514-9391-a167483b4b7b" />


**Note**: it changes the interfaces state to down and it brings it back up

## 3️⃣ Disable DTP on both interfaces:

```bash
switchport nonegotiate
```

## 4️⃣ Verify administrative and operational mode:

```bash
end
show interfaces G0/1 switchport
```

**Expected output ✅:**

<img width="542" height="173" alt="T1-show-SW2-sp-g01" src="https://github.com/user-attachments/assets/bf1e182a-7d8f-4b96-8c18-a4ff4b0433c4" />

<br>
<br>

```bash
show interfaces G0/2 switchport
```

**Expected output ✅:**

<img width="527" height="174" alt="T1-show-SW2-sp-g02" src="https://github.com/user-attachments/assets/1d000caa-ec91-4c94-a62f-7f39e2af142c" />

## 5️⃣ Check running-config
```bash
show run
```

**Expected output ✅:**

<img width="463" height="169" alt="T1-RC-SW2" src="https://github.com/user-attachments/assets/d2da235f-c9c7-416e-b137-9345aa3e1661" />

## 6️⃣ save config 
```bash
write memory
```

<br>
<br>

# 🧩 SW3: Configure G0/1 as trunk & disable DTP

<br>

## 1️⃣ Enter global configuration mode:
```bash
enable
configure terminal
```

## 2️⃣ Enter interface configuration for G0/1 and configure as trunk:
```bash
interface G0/1
switchport mode trunk
```

## 3️⃣ Disable DTP on the interface:

```bash
switchport nonegotiate
```

## 4️⃣ Verify administrative and operational mode:
```bash
do show interfaces G0/1 switchport
```

**Expected output ✅:**

<img width="529" height="169" alt="T1-show-SW3-sp-g01" src="https://github.com/user-attachments/assets/76ffb50b-1a76-4283-8c62-2021196fdeab" />


## 5️⃣ Check running-config

```bash
show run
```

**Expected output ✅:**

<img width="369" height="99" alt="T1-RC-SW3" src="https://github.com/user-attachments/assets/105ad70f-f401-40e7-98cd-5a7df44e80e6" />

## 6️⃣ save config 
```bash
write memory
```

