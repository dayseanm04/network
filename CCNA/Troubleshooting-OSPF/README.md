# Configuring and Troulbeshooting OSPF – Lab Part 3 🧭🖧

## Topology For Reference

<img width="707" height="307" alt="topololgy" src="https://github.com/user-attachments/assets/1bbf3291-df9e-4c4b-b4b6-a049225a6423" />

## 📌 Summary
This lab focuses on troubleshooting and fixing OSPF issues in a pre-configured network.  
I will configure a new serial link, verify OSPF adjacencies, resolve routing problems, restore external connectivity, and examine the OSPF Link-State Database (LSDB).

---


## 🗂️ Tasks

### 📝 Task 1A: Configure Serial Connection Between R1 and R2
Configure the serial link between R1 and R2, including setting the clock rate to **128000** where required.

### 🌐 Task 1B: Configure OSPF on R1 and R2
Enable OSPF on the new serial connection so routing information can be exchanged.

### 🔍 Task 2: Fix Missing Route to 10.0.2.0/24
Only R3 has a route to the 10.0.2.0/24 network.  
Identify why other routers do not have this route and correct the issue.

### 🔄 Task 3: Fix OSPF Neighbor Issue With R5
R2 and R4 are not forming OSPF neighbor relationships with R5.  
Determine the cause and fix the problem so adjacencies can form.

### 🌍 Task 4: Restore Connectivity to External Server (8.8.8.8)
PC1 and PC2 are unable to ping the external server 8.8.8.8.  
Troubleshoot the issue and restore end-to-end connectivity.

### 📚 Task 5: Examine the OSPF LSDB
Inspect the OSPF Link-State Database and identify which LSAs are present.


---

### ✍️ Author Information
Name: Daysean Mensah <br/>
Course/Program: Cisco CCNA Studies <br/>
Lab completion date: Dec 13 2025. <br/>
