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

**SW4:** has two equal-cost paths (400,000) via SW2 and SW3

<img width="667" height="406" alt="T2-SW4-RC1" src="https://github.com/user-attachments/assets/774d1589-b710-4fb1-8b45-2de646bf1627" />

- Tie-breaker → lowest Bridge ID of the neighbor
- SW3 has the lowest MAC address

### Topology with STP ports:
<img width="679" height="427" alt="T2-rstp-ports2" src="https://github.com/user-attachments/assets/686fd7b4-f7ba-4fc1-a34a-e01a58fb55a1" />

- **SW4 F0/1** will be the root port  
- **SW4 F0/2** will be Alternate (Discarding)

## Designated Port and Alternate ports decisions 🏆

**SW4 ↔ SW2 segment:**

<img width="679" height="425" alt="SW4-SW2-RC" src="https://github.com/user-attachments/assets/45da9272-43ff-480b-88e5-8e61993acd56" />

- SW2 has the lower root cost (200k) →  SW2 F0/2 becomes the Designated Port
- SW4  root cost is 400k so its F0/2 becomes Alternate (Discarding)


**SW3 ↔ SW2 segment:**

<img width="679" height="427" alt="SW3-SW2-RC" src="https://github.com/user-attachments/assets/adb5c411-973d-462c-81d5-2f55da727cd1" />

- SW3 and SW2 both have equal root cost → tie-breaker = lower MAC address
- Since all the switches have the same priority. SW3 has the lower MAC address so SW3 G0/1 becomes the Designated Port
- SW2 G0/1 becomes Alternate (Discarding)

## Verification with CLI 🖥️

**On SW2 in Priviliged EXEC mode:**
```bash
show spanning-tree
```

**Expected output✅:**

<img width="787" height="395" alt="T2-show-stp-SW2" src="https://github.com/user-attachments/assets/abb4ae92-9339-45ad-b773-4987b854b032" />

<br/><br/>

**On SW3 in Priviliged EXEC mode:**
```bash
show spanning-tree
```

**Expected output✅:**

<img width="785" height="366" alt="T2-show-stp-SW3" src="https://github.com/user-attachments/assets/a5964a71-ed8b-4ab9-868d-f15e932c448b" />

<br/><br/>

**On SW4 in Priviliged EXEC mode:**
```bash
show spanning-tree
```

**Expected output✅:**

<img width="785" height="352" alt="T2-show-stp-SW4" src="https://github.com/user-attachments/assets/714de731-895a-433b-9996-be68f3a909d4" />
