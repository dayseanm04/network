# 💻 PC Configuration (Task 5)

## 🧠 Objective
Configure IPv6 addresses and default gateways on each PC to enable IPv6 communication across the dual-stack network.

---

## 📋 IPv6 Configuration Summary

| PC  | IPv6 Address            |  Prefix | Default Gateway       |
|-----|--------------------------|----------------|------------------------|
| PC1 | 2001:DB8:0:1::2          | /64            | 2001:DB8:0:1::1        |
| PC2 | 2001:DB8:0:2::2          | /64            | 2001:DB8:0:2::1        |
| PC3 | 2001:DB8:0:3::2          | /64            | 2001:DB8:0:3::1        |

---

## 🖥️ PC1 Config

1. Click on **PC1** .  
2. Go to the **Config** tab.  
3. Under **Global Settings** and **IPv6 Default Gateway** and enter: 2001:DB8:0:1::1
4. Click on **FastEthernet0** from the left panel.  
5. In the **IPv6 Address** field, enter: 2001:DB8:0:1::2/64
6. Close the window


---

## 🖥️ PC2 Config

1. Click on **PC2** in Packet Tracer.  
2. Go to the **Config** tab.  
3. Under **Global Settings**, enter the **IPv6 Default Gateway**: 2001:DB8:0:2::1
4. Click on **FastEthernet0** from the left panel.
5. In the **IPv6 Address** field, enter: 2001:DB8:0:2::2/64
6. Close the window

---

## 🖥️ PC3 Config

1. Click on **PC3** in Packet Tracer.  
2. Go to the **Config** tab.  
3. Under **Global Settings**, set the **IPv6 Default Gateway**: 2001:DB8:0:3::1
4. Click on **FastEthernet0** from the left panel.
5. In the **IPv6 Address** field, enter: 2001:DB8:0:3::2/64
6. Close the window
