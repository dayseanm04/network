# 🧪 Test BPDU Guard Behavior

## 🔌 Test Scenario:
<img width="459" height="279" alt="BPDU-Gaurd-test1" src="https://github.com/user-attachments/assets/ce542217-64e3-4442-8af8-e0d3d9a7e0eb" />

- PortFast and BPDUGuard is enabled on SW3 & SW4 F0/3 interface
- Disconnect SW3 F0/3 from PC1.


<img width="502" height="297" alt="BPDU-Gaurd-test" src="https://github.com/user-attachments/assets/87d3225f-3090-40a9-a6e3-84db000ae0a6" />

Use a crossover cable to connect:
- SW3 F0/3 → SW4 F0/4

## 🔍 What happened?
- SW3’s F0/3 port immediately went down (err-disabled).
- This occurred because the interface received a BPDU while BPDU Guard was enabled.
- BPDU Guard shuts down the port to protect the network from loops.
- You should see the link light turn red.
