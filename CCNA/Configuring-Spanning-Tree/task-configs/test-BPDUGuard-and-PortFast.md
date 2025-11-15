# 🧪 Test BPDU Guard Behavior

## 🔌 Test Scenario:

### Remove the connection between SW3 F0/3 interface & PC1:

<img width="459" height="279" alt="BPDU-Gaurd-test1" src="https://github.com/user-attachments/assets/24ea8fe0-097c-4058-96d1-982783d379e7" />

- PortFast and BPDUGuard is enabled on **SW3** & **SW4 F0/3** interface
- Disconnect **SW3 F0/3** from **PC1**.

### Connect SW3 F0/3 interface to SW4 F0/4 interface:

<img width="502" height="297" alt="BPDU-Gaurd-test" src="https://github.com/user-attachments/assets/49694d67-065f-4c7a-8f12-2bd7fdf8f678" />

Use a crossover cable to connect:
- **SW3 F0/3** → **SW4 F0/4**

### Expected output in SW3 CLI✅:

<img width="877" height="235" alt="SW3-BPDUGuard-err" src="https://github.com/user-attachments/assets/e977f941-c925-4538-944c-7f55b320dc65" />


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

### In interface config mode for SW3's F0/3 interface:
```bash
shutdown
no shutdown
```

### Expeced output ✅:
<img width="443" height="285" alt="BPDU-Gaurd-test3" src="https://github.com/user-attachments/assets/50d1013b-e32c-4a2e-a6c3-774c4d876fa6" />


# 🧪 Test PortFast Behavior

## 🔌 Test Scenario:

### Remove the connection between SW4 F0/3 interface & PC2:
<img width="570" height="379" alt="SW3-portfast-test" src="https://github.com/user-attachments/assets/f6e38e5d-aa62-44bf-9eae-64e708bd70be" />


### Now connect SW4 F0/3 interface & PC2:
<img width="454" height="294" alt="SW3-portfast-test-2" src="https://github.com/user-attachments/assets/ccb1ffdd-115e-4106-b5b3-32fcccdef730" />

- Notice how fast the link lights turn green.
- Why? PortFast allows switch ports connected to end hosts to immediately enter the STP forwarding state, bypassing listening and learning states.
