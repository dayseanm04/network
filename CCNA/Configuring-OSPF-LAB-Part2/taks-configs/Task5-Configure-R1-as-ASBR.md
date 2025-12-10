# Task5-Configure-R1-as-ASBR.md

## 🎯 Objective  
Configure **R1** as an Autonomous System Border Router (ASBR) that advertises a **default route** into the OSPF domain.


## Topology For Reference

<img width="711" height="341" alt="Topology" src="https://github.com/user-attachments/assets/53e6080d-57be-4f5f-b410-c3046016c538" />

---

## 🛠️ Configure Default Route on R1

### 1️⃣ **Enter privileged EXEC mode**

```bash
enable
```

### 2️⃣ View the current routing table (optional check)

```bash
show ip route
```

**Expected Ouput ✅:**

<img width="906" height="472" alt="T5-R1-show-route" src="https://github.com/user-attachments/assets/ac58aad8-acd8-476b-8f24-373088019fc6" />

**Note: There is no default route on R1.**

### 3️⃣ Enter global configuration mode

```bash
configure terminal
```

### 4️⃣ Configure a static default route pointing toward the ISP

```bash
ip route 0.0.0.0 0.0.0.0 202.0.113.2
```

### 5️⃣ Exit back to privileged EXEC mode

```bash
end
```

### 6️⃣ Verify that the default route is now in the routing table

```bash
show ip route
```

**Expected Ouput ✅:**

<img width="830" height="497" alt="T5-R1-show-route-after" src="https://github.com/user-attachments/assets/f173d820-4858-4c75-aef9-dde02da2a3f8" />

## 🌐 Step-by-Step: Advertise Default Route into OSPF

### 7️⃣ Re-enter global configuration mode

```bash
conf terminal
```

### 8️⃣ Enter OSPF configuration mode (process 1)


```bash
router ospf 1
```

### 9️⃣ Advertise the default route into the OSPF domain

```bash
default-information originate
```

### 🔟 Verify

```bash
do show ip protocols
```

**Expected Ouput ✅:**

<img width="766" height="421" alt="T5-R1-ASBR" src="https://github.com/user-attachments/assets/51eaae63-1b89-4a97-8cb8-2f494beb3ac1" />

**R1 is not an ASBR**
