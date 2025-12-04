# 🚦 Task 2: Configure Floating Static Routes

## 🎯 Goal
In this task I will configure **floating static routes** on **R1** and **R2** so that PC1 can still reach SRV1 if the direct link between R1 and R2 goes down.

<br/>

A floating static route is just a normal static route with a **higher administrative distance (AD)** than the dynamic protocol (OSPF).  
- OSPF AD = 110  
- Floating static route AD = 115 (backup route)

