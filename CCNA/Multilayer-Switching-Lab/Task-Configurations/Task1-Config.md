# 🧩 Multilayer Switching Lab

# Task 1 Config 🛠️
Step-by-step configuration for **Task 1** replacing ROAS with a point-to-point Layer 3 connection between **R1** and **SW2**.

---

## 1) Remove subinterfaces on R1 🧹
Enter global config mode:
```bash
enable
configure terminal
```

## 1️⃣ (Optional) Show current interfaces and subinterfaces:
```bash
do show ip interface brief
```

### Expected Output ✅
<img width="822" height="192" alt="R1-ip-int" src="https://github.com/user-attachments/assets/aa03ea67-b455-456a-884d-8ef253db0d86" />


## 2️⃣ Remove the ROAS subinterfaces:
```bash
no interface GigabitEthernet0/0.10
no interface GigabitEthernet0/0.20
no interface GigabitEthernet0/0.30
```

## 3️⃣ Verify subinterfaces are removed:
```bash
do show ip interface brief
```

### Expected Output ✅:
<img width="842" height="140" alt="R1-sub-int-rmvd" src="https://github.com/user-attachments/assets/44b82e10-98f6-4105-baea-c1f8b2bb8ac4" />


---

## 2) Reset R1 g0/0 interface to defaults 🔁

## 1️⃣ In global config mode:
```bash
default interface G0/0
```

## 2️⃣ Verify the interface state:
```
do show ip interface brief
```

---

## 3) Configure the point-to-point link on R1 ⚙️

## 1️⃣ Enter interface config for g0/0 and set the IP for the /30 point-to-point link:
```bash
int G0/0
ip address 10.0.0.194 255.255.255.252
no shutdown
```

## 2️⃣ Exit and check:
```bash
end
show ip interface brief | include GigabitEthernet0/0
```

### Expected Output ✅:
<img width="767" height="84" alt="Verifiy-p2p-r1" src="https://github.com/user-attachments/assets/ffa66e7c-e1b6-4696-889d-6912231928f8" />


## 3️⃣ Save the router config:
```bash
write memory
```

---

## 4) Configure point-to-point on SW2 (change G1/0/2 to a L3 port + enable IP routing) 🔌
### On SW2 (multilayer switch):

## 1️⃣ Enter global config and enable IP routing:
```bash
en
conf t
ip routing
```

## 2️⃣ Change SW2 G1/0/2 interface to a Layer 3 port and assigned IP 10.0.0.193/30:
```bash
int G1/0/2
no switchport
ip addr 10.0.0.193 255.255.255.252
no shutdown
```

## 3️⃣ Verify the L3 interface and switch IPs:
```bash
do show ip interface brief
```

### Expected Output ✅:
<img width="819" height="155" alt="verify-sw-ip-int-p2p" src="https://github.com/user-attachments/assets/4116edb9-ba34-4790-af35-7468d3cdafb8" />

```bash
do show interface status
```

### Expected Output ✅:
<img width="818" height="154" alt="SW2-int-status" src="https://github.com/user-attachments/assets/b7bba67a-5c7e-4163-9063-747656417ac9" />

---

## 5) Configure default route on SW2 ➡️
## 1️⃣ Configure a default route on the multilayer switch pointing to R1's g0/0:
```bash
configure terminal
ip route 0.0.0.0 0.0.0.0 10.0.0.194
end
```

## 2️⃣ Verify the default route:
```bash
do show ip route
```

### Expected Output ✅:
<img width="809" height="277" alt="SW2-verify-route" src="https://github.com/user-attachments/assets/28c71843-13df-4018-8321-d2c94a6432c3" />

## 3️⃣ Save config
```bash
write memory
```
