# 🧠 Analyzing STP Lab

This repository contains my work for the **Analyzing Spanning Tree Protocol (STP)** lab.  
The purpose of this lab is to observe and analyze how STP determines:

- ⭐ The **root bridge**
- 🔌 The **role** of each switch port (Root, Designated, or Non-Designated)

This lab focuses on learning how STP makes decisions based on **Bridge ID**, **path cost**, and **port roles** to ensure a loop-free Layer 2 topology.

## 🧭 Navigation

Use this section to quickly access each part of the lab:

### 📂 Main Files
- 📘 [README.md](./README.md) — Overview of the STP analysis lab  
- 📝 [task1.md](./task1.md) — Determine which switch is the root bridge  
- 🔍 [task2-calculate-root-cost.md](./task2-calculate-root-cost.md) — Calculate STP root path cost  
- 🔌 [task2-find-root-port.md](./task2-find-root-port.md) — Identify each switch’s root port  
- 🔄 [task2-find-designated-and-non-designated-ports.md](./task2-find-designated-and-non-designated-ports.md) — Determine designated & non-designated ports  


## 📘 Lab Overview

This lab was completed using several interconnected switches running **Spanning Tree Protocol (STP)**.  
The objective is to analyze the current STP topology using show commands and determine how STP elects the root bridge and assigns port roles.
