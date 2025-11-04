# Root Cost Calculations

**📝 Caluclate the Root: the total cost of the outgoing interfaces + the path to the root bridge.**

**Note:** Each switch can only have 1 root port

## ⚡ STP Port Cost Reference

| **Interface Speed** | **STP Cost** |
|----------------------|--------------|
| FastEthernet (100 Mbps) | 19 |
| GigabitEthernet (1 Gbps) | 4 |


STP uses these costs to decide which path to the Root Bridge is the best (lowest cost).

---

Since **SW3** is the root bridge all of its interface will have a root cost of **0**. so it will advertise the root cost of **0** out of all its interfaces like this. See below: 

<img width="530" height="361" alt="SW3-advertise" src="https://github.com/user-attachments/assets/935b4b0f-280b-4662-8501-73a217f1330b" />


<br><br>

**SW1 F0/3** and **F0/4** interface will advertise the root cost of 19 to **SW1 F0/1** and **F0/2** interface because its outgoing interfaces are FastEthernet ports with the cost of 19, so **19 + 0** (**SW3 F0/1** and **F0/2** interface cost) is **19**. See below:

<img width="510" height="326" alt="SW1-F12-cost" src="https://github.com/user-attachments/assets/b6b92342-96e8-4b22-84ea-b4611c0ede30" />

<br><br>

**SW1 F0/1** and **F0/2** interfaces will advertise the root cost of **38** to the Root Bridge **SW3 F0/3** interface because **SW1 F0/1** and **F0/2** outgoing interfaces are FastEthernet ports with the cost of **19**, and the cost of **SW2 F0/3** interface is also **19**, so **19 + 19 + 0** (**SW3 F0/3** interface cost) is **38.** See bellow:

<img width="632" height="347" alt="SW1-F01-SW3-F03" src="https://github.com/user-attachments/assets/adeb383b-77fa-4057-881d-a0ead6e78ac4" />

<br><br>

**SW1 F0/1** and **F0/2** interfaces will adevertise the root cost of **27** to the Root Bridge **SW3 G0/1** interface because **SW1 F0/1** and **F0/2** outgoing interfaces are FastEthernet ports with the cost of **19**, and the cost of **SW2 G0/1** interface is **4**, and the cost of **SW4 G0/2** interface is also **4**, so **19 + 4 + 4 + 0** (**SW3 G0/1** interface cost) is **27.** See bellow:

<img width="632" height="347" alt="SW1-F012-cost" src="https://github.com/user-attachments/assets/a2c58808-5827-4abe-bffb-beb56fa79ecc" />

<br><br>

**SW2 F0/3** interface will adevertise the root cost of **19** to the Root Bridge **SW3 F0/3** interface, because its outgoing interface is a FastEthernet port with a cost of **19**, so **19 + 0** (**SW3 F0/3** interface cost) is **19**. See below:

<img width="592" height="307" alt="SW2-F03-cost" src="https://github.com/user-attachments/assets/b90d83ee-5201-46e1-9d4e-76a0d831c110" />

<br><br>

**SW2 G0/1** interface will adevertise the root cost of **8** to the Root Bridge **SW3 G0/1** interface, because its outgoing interface is a GigabitEthernet port with a cost of **4**, and the cost of **SW4 G0/2** interface is also **4**, so **4 + 4 + 0** (**SW3 G0/1** interface cost) is **8**. See below:

<img width="636" height="351" alt="SW2-G01-cost" src="https://github.com/user-attachments/assets/0035bcfd-d000-4c7b-8a75-7a8bc6824a2b" />

<br><br>

**SW2 F0/1 & F0/2** interfaces will advertise the root cost of **38** to the Root Bridge **SW3 F0/1 & F0/2** interfaces because **SW2 F0/1 & F0/2** outgoing interfaces are FastEthernet ports with the cost of **19**, and the cost of **SW1 F0/3 & F0/4** interfaces are also **19**, so **19 + 19 + 0** (**SW3 F0/1 & F0/2** interfaces cost) is **38.** See bellow:

<img width="632" height="347" alt="SW2-F012-cost" src="https://github.com/user-attachments/assets/e2a94e95-438b-4be1-bf90-51e6ea231798" />

<br><br>

**SW4 G0/2** interface will adevertise the root cost of **4** to the Root Bridge **SW3 G0/1** interface, because its outgoing interface is a GigabitEthernet port with a cost of **4**, so **4 + 0** (**SW3 G0/1** interface cost) is **4**. See below:

<img width="632" height="347" alt="SW4-advertise-G02" src="https://github.com/user-attachments/assets/f80acbcd-8572-4dfb-b8c3-45d6688286f2" />

<br><br>

**SW4 G0/1** interface will advertise the root cost of **42** to the Root Bridge **SW3 F0/1 & F0/2** interfaces because **SW4 G0/1** outgoing interface is a GigabitEthernet port with the cost of **4**, and the cost of **SW2 F0/1 & F0/2** interfaces are **19**, and the cost of **SW1 F0/3 & F0/4** interfaces are also **19**, so **4 + 19 + 19 + 0** (**SW3 F0/1 & F0/2** interfaces cost) is **42.** See bellow:

<img width="632" height="347" alt="SW4-G01-SW3-012" src="https://github.com/user-attachments/assets/dd7abcd4-e650-42de-90ec-f1dae0a8993d" />

<br><br>

**SW4 G0/1** interface will advertise the root cost of **23** to the Root Bridge **SW3 F0/3** interface because **SW4 G0/1** outgoing interface is a GigabitEthernet port with the cost of **4**, and the cost of **SW2 F0/3** interface is **19**, so **4 + 19  + 0** (**SW3 F0/3** interface cost) is **23.** See bellow:

<img width="632" height="347" alt="SW4-G01-to-SW3-F03" src="https://github.com/user-attachments/assets/4a562fc1-a16c-41fe-bf71-fd15e5fb3b06" />
