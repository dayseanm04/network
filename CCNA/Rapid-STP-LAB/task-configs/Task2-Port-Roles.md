# Task 2: Determine Port Roles & States 🔌

### Purpose of This Task 🎯
- Determine the RSTP port roles and states on every switch.
- First predict the roles WITHOUT using the CLI.
- Then confirm using the "show spanning-tree" command.
- Apply RSTP root cost rules and tie-breaker logic between switches.  

### RSTP Port Cost Reference 📊
- FastEthernet (100 Mbps) = 200,000
- GigabitEthernet (1 Gbps) = 20,000  

## Topology For Reference:
<img width="679" height="427" alt="Topology" src="https://github.com/user-attachments/assets/eec8b2e8-5a63-4614-8f58-e55a9f4b7c18" />

## Root Ports on Each Switch 🌐
- **SW2:** F0/1 interface is the root port. (Direct connection to SW1, the Root Bridge)
- **SW3:** F0/2 is the root port. (Connected through the hub segment to SW1)

## Topology with STP ports:
<img width="679" height="427" alt="T2-rstp-ports1" src="https://github.com/user-attachments/assets/49b3bb28-23d7-4065-a2b7-2ac11118ca03" />

