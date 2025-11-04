### More Details below

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

<img width="530" height="361" alt="SW3-advertise" src="https://github.com/user-attachments/assets/dec438f3-bb35-4f8f-96e6-aad4f31ef763" />

<br><br>

**SW1 F0/3** and **F0/4** interface will advertise the root cost of 19 to **SW1 F0/1** and **F0/2** interface because its outgoing interfaces are FastEthernet ports with the cost of 19, so **19 + 0** (**SW3 F0/1** and **F0/2** interface cost) is **19**. See below:

<img width="510" height="326" alt="SW1-F12-cost" src="https://github.com/user-attachments/assets/788aac69-5a7d-4992-897f-40c86fc18c76" />

<br><br>

**SW1 F0/1** and **F0/2** interfaces will advertise the root cost of **38** to the Root Bridge **SW3 F0/3** interface because **SW1 F0/1** and **F0/2** outgoing interfaces are FastEthernet ports with the cost of **19**, and the cost of **SW2 F0/3** interface is also **19**, so **19 + 19 + 0** (**SW3 F0/3** interface cost) is **38.** See bellow:

<img width="632" height="347" alt="SW1-F01-SW3-F03" src="https://github.com/user-attachments/assets/d1b0c314-39e2-4be6-8789-95809ea21549" />

<br><br>

**SW1 F0/1** and **F0/2** interfaces will adevertise the root cost of **27** to the Root Bridge **SW3 G0/1** interface because **SW1 F0/1** and **F0/2** outgoing interfaces are FastEthernet ports with the cost of **19**, and the cost of **SW2 G0/1** interface is **4**, and the cost of **SW4 G0/2** interface is also **4**, so **19 + 4 + 4 + 0** (**SW3 G0/1** interface cost) is **27.** See bellow:

<img width="632" height="347" alt="SW1-F012-cost" src="https://github.com/user-attachments/assets/f8dde9b2-0548-42a9-b2f6-1455e2af0422" />

<br><br>

**SW2 F0/3** interface will adevertise the root cost of **19** to the Root Bridge **SW3 F0/3** interface, because its outgoing interface is a FastEthernet port with a cost of **19**, so **19 + 0** (**SW3 F0/3** interface cost) is **19**. See below:

<img width="592" height="307" alt="SW2-F03-cost" src="https://github.com/user-attachments/assets/b90d83ee-5201-46e1-9d4e-76a0d831c110" />

<br><br>

**SW2 G0/1** interface will adevertise the root cost of **8** to the Root Bridge **SW3 G0/1** interface, because its outgoing interface is a GigabitEthernet port with a cost of **4**, and the cost of **SW4 G0/2** interface is also **4**, so **4 + 4 + 0** (**SW3 G0/1** interface cost) is **8**. See below:

<img width="636" height="351" alt="SW2-G01-cost" src="https://github.com/user-attachments/assets/0035bcfd-d000-4c7b-8a75-7a8bc6824a2b" />

<br><br>

**SW4 G0/2** interface will adevertise the root cost of **4** to the Root Bridge **SW3 G0/1** interface, because its outgoing interface is a GigabitEthernet port with a cost of **4**, so **4 + 0** (**SW3 G0/1** interface cost) is **4**. See below:

<img width="632" height="347" alt="SW4-advertise-G02" src="https://github.com/user-attachments/assets/f80acbcd-8572-4dfb-b8c3-45d6688286f2" />

<br><br>
