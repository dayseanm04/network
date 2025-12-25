# 🧩 Task 2 – Configure R1 G0/0 as a DHCP Client

## 🎯 Goal
Configure **R1’s G0/0 interface** to obtain an IP address automatically using **DHCP**. Then verify what IP address it receives from **R2**.

## Topology For Reference

<img width="645" height="285" alt="Topology" src="https://github.com/user-attachments/assets/21f639d4-6d6f-4952-9de3-d255df077e99" />

---

## ✅ Configure R1

### 2️⃣ Enter Privileged EXEC Mode

```bash
enable
configure terminal
```


### 2️⃣ Enter Interface Configuration Mode (G0/0)

```bash
interface g0/0
no shutdown
```

### 3️⃣ Configure G0/0 to Get an IP Address via DHCP

```bash
ip address dhcp
```

**Expected Log message✅:**

<img width="965" height="90" alt="T2-R1-log" src="https://github.com/user-attachments/assets/1dcde51e-c097-4871-a240-223e42b2e60a" />



## 🔍 Verify the IP Address on R1

On **R1**, verify the address assigned to G0/0:

```bash
show ip interface brief
```

**Expected Output✅:**

<img width="822" height="138" alt="T2-show-int-brief" src="https://github.com/user-attachments/assets/6780f5cb-fb55-4439-867f-ad201e5c40ed" />

---

On **R2**, verify the address assigned to G0/0:

```bash
show ip dhcp binding
```

**Expected Output✅:**

<img width="765" height="96" alt="T2-R2-DHCP-binding" src="https://github.com/user-attachments/assets/487d52ef-57ff-4f0d-aa54-362203f34635" />
