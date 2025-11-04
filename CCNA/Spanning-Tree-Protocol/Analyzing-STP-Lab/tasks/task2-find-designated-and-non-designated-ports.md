# ⚙️ Task 2: Identify the designated and Non-designated ports

## 🎯 Objective

Identify Designated and Non-Designated Ports on each non root switch

## Topology For Reference with root ports
<img width="632" height="347" alt="RootPorts" src="https://github.com/user-attachments/assets/20dc4fd4-0aa7-4053-9eb2-511c46662a6a" />


## 🧩 Identify Designated Ports
- The interface connected to a root port is a designated port

**See Below:** <br>
<img width="632" height="347" alt="DP-topology" src="https://github.com/user-attachments/assets/06be4df2-508b-4394-9d07-a00f280ca1db" />



## 🧩 Identify Non-Designated Ports

- SW1 F0/3 is connected to the Root Bridge (SW3) so its a Non designated Port
- SW2 F0/3 is connected to the Root Bridge (SW3) so its a Non designated Port

**See Below:**  <br><br>
<img width="632" height="347" alt="NDP-topology - Copy" src="https://github.com/user-attachments/assets/c8dc12e0-d34f-46ef-8942-36ff7e20eb78" />

## 🧩 Identify Designated & Non-Designated Ports between SW1 & SW2

### Topology For reference
<img width="636" height="351" alt="DP-topology" src="https://github.com/user-attachments/assets/29fee29c-7d5c-4368-8192-a08e4f4ec3e7" />



### The interfaces on the switch with the lower root cost will be designated the other side will be non designated.
- SW1 root cost is 19 via F0/4
- SW2 root cost is 8 via G0/1 (**Lowest Root Cost ✅**)
- SW2 F0/1 and F0/2 interfaces will be **designated ports.**
- SW1 F0/1 and F0/2 interfaces will be **non-designated.**

🔗 **[Click here to view how to calculate the root cost →](./task2-calculate-root-cost.md)**


**See Below:**  <br><br>
<img width="632" height="347" alt="DP_NDP-topology - Copy - Copy" src="https://github.com/user-attachments/assets/c95dea79-4af4-4d6d-83b3-1a23f5b932d1" />

