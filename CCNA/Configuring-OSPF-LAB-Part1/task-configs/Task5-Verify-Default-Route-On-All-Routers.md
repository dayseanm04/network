# 📘 Verify Default Routes on R2, R3, and R4

## Topology For Reference

<img width="711" height="341" alt="Topology" src="https://github.com/user-attachments/assets/53e6080d-57be-4f5f-b410-c3046016c538" />

### 1️⃣ Enter privileged EXEC mode:

```bash
enable
```
### 2️⃣ Check the routing table on each router

```bash
show ip route
```

### R2 Expected Ouput ✅:

<img width="834" height="507" alt="T5-R2-show-ip-route" src="https://github.com/user-attachments/assets/2fb75f66-5afb-498d-a54c-825312957ea6" />

### R3 Expected Ouput ✅:

<img width="881" height="501" alt="T5-R3-show-ip-route" src="https://github.com/user-attachments/assets/f9769442-440d-460a-88e7-fea08d3ae75f" />

### R4 Expected Ouput ✅:

<img width="814" height="516" alt="T5-R4-show-ip-route" src="https://github.com/user-attachments/assets/39b57499-3b2b-4ecc-b9e7-4b7d3c88c898" />

This means:
- The default route is coming from OSPF.
- It is an external (E2) route originated by R1 (the ASBR).
- Now, all routers R2, R3, and R4 know how to send traffic to networks outside the OSPF domain using R1 as their gateway.

**The default route were added to all of the routers**

### Other OSPF Verification commands

- show ip ospf neighbor
- show ip ospf interface
