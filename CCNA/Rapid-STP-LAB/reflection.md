# Reflection: Rapid-STP Lab 💭

## Overview 📝

This lab helped me understand how Rapid Spanning Tree Protocol (RSTP)
makes decisions in a real switching environment. By working through
each task, I gained hands-on experience with port roles, link types,
root path cost calculations, and how hubs affect the topology.

## Key Takeaways 📚

- RSTP converges much faster than classic STP and introduces new
  port roles: Alternate and Backup ports.
- The Root Bridge is not always obvious: even when all switch
  priorities are the same, MAC addresses become the deciding factor.
- Real Cisco switches display both link type (point-to-point/shared)
  and edge status, even although Packet Tracer didnt.

- The `show spanning-tree` command is important for :
  - Verifying roles
  - Checking link types
  - Confirming root cost

## What I Learned 💡
- How to analyze a full RSTP topology without relying on the CLI.  
- How RSTP uses tie-breakers (Bridge ID, port ID) when multiple paths have the same cost.
- Why RSTP handles hubs differently and why only one designated port can exist per collision domain.

## Final Thoughts 🌟

This lab gave me practical experience with RSTP beyond just theory.
Understanding how RSTP behaves with mixed link types, hubs, and
multiple switches helped strengthen my
overall knowledge of Layer 2 networking.

