# 🌐 Rapid-STP Lab

The lab focuses on identifying the root bridge, analyzing port roles, calculating root costs, and configuring RSTP link types across a multi-switch topology.

## Topology For Reference:
<img width="679" height="427" alt="Topology" src="https://github.com/user-attachments/assets/27ae675a-95d0-4369-9a98-b1d2222f65ec" />

# 📘 Overview

- Understand how RSTP selects the root bridge.
- Analyze RSTP port roles and states.
- Calculate root path costs between switches.
- Configure RSTP link types (point-to-point, shared, edge).
- Observe how hubs affect collision domains.
- Verify all results using the CLI (show spanning-tree).

## 🧰 Devices Used
- 4 Cisco 2960-24TT switches
- 2 Hubs
- 5 PCs (PC1–PC5)

# 🧪 Tasks (Summary)

### Task 1: Identify the Root Bridge:

- Determine which switch becomes the root bridge.
- Examine port roles/states on the root switch.
- Full details in: Task1-Root-Bridge.md

### Task 2: Determine Port Roles & States for each Switch
- Determine RSTP roles/states without using the CLI.
- Calculate RSTP path costs.
- Use tie-breakers (lowest bridge ID).
- Confirm using CLI outputs.
- Full details in: Task2-Port-Roles.md


### Task 3: Configure RSTP Link Types
- Configure point-to-point, shared, and edge ports.
- Understand how hubs affect link type selection.
- Verify link type using "show spanning-tree".
- Full details in: Task3-RSTP-Link-Types.md

## Navigation

pkt-files 📁
----------------------------------------------------
- Packet Tracer blank lab: [Rapid-STP-LAB-Blank.pkt](pkt-files/Rapid-STP-LAB-Blank.pkt)
- Packet Tracer completed lab: [Rapid-STP-LAB-Completed.pkt](pkt-files/Rapid-STP-LAB-Completed.pkt)


task-configs 📁
----------------------------------------------------
- Task 1: Root Bridge: [Task1-Root-Bridge.md](task-configs/Task1-Root-Bridge.md)
- Task 2: Port Roles & States: [Task2-Port-Roles.md](task-configs/Task2-Port-Roles.md)
- Task 3:RSTP Link Types: [Task3-RSTP-Link-Types.md](task-configs/Task3-RSTP-Link-Types.md)

- Reflection: [reflection.md](reflection.md)
 - Personal reflection summarizing lessons learned from the lab.


# 🧠 Summary

### This lab help me understand :
- How RSTP converges quickly after topology changes.
- How root, designated, alternate, and backup ports are selected.
- How collision domains and hubs affect spanning tree decisions.
- Difference between link types: shared, point-to-point, and edge.
- How to configure and verify all RSTP settings in cisco IOS.

---


**Name:** *Daysean Mensah*  
**Course/Program:** *Cisco CCNA Studies*  
**Lab completion date:** Novemeber 17 2025.
