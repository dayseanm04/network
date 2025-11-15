# 🧪 Test BPDU Guard Behavior

## 🔌 Test Scenario:

<img width="459" height="279" alt="BPDU-Gaurd-test1" src="https://github.com/user-attachments/assets/24ea8fe0-097c-4058-96d1-982783d379e7" />

- PortFast and BPDUGuard is enabled on SW3 & SW4 F0/3 interface
- Disconnect SW3 F0/3 from PC1.


<img width="502" height="297" alt="BPDU-Gaurd-test" src="https://github.com/user-attachments/assets/49694d67-065f-4c7a-8f12-2bd7fdf8f678" />

Use a crossover cable to connect:
- **SW3 F0/3** → **SW4 F0/4**

## 🔍 What happened?
- **SW3’s F0/3** port immediately went down (err-disabled).
- This occurred because the interface received a BPDU while BPDU Guard was enabled.
- BPDU Guard shuts down the port to protect the network from loops.
- You should see the link light turn red.

**Note: in order to renable the interface you have to fix the problem first then re-enable the interface**

## Fix: 🔧Re-enable the Port After Testing

<img width="469" height="297" alt="BPDU-Gaurd-test2" src="https://github.com/user-attachments/assets/a9678d9e-bea8-42fe-9037-47e0e20ce16e" />

- Now remove that connection and connect **SW3 f0/3** interface to **PC1** again
- Link light is still red
