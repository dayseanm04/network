# 🧪 Task 2 – Test NAT Pool Exhaustion (Dynamic NAT)

## 🎯 Goal
Test what happens when the **Dynamic NAT pool runs out of available public IP addresses**.

In this lab, the NAT pool only has **two public IPs** (`100.0.0.1` and `100.0.0.2`). 
That means only **two inside hosts** can successfully access the internet at the same time using Dynamic NAT.
When a third host tries, it should fail.

## Topology For Reference

<img width="588" height="215" alt="Topology" src="https://github.com/user-attachments/assets/a0ad75ab-6982-416a-8c01-5fd83306f1b0" />

---
