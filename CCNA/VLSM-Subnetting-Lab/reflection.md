# Reflection on VLSM Subnetting Lab

## Summary of the Lab

In this lab, I used Variable Length Subnet Masking (VLSM) to efficiently allocate IP addresses for multiple LANs and a point-to-point connection between routers. The lab involved four main tasks:

1. **Subnetting the 192.168.5.0/24 network** to provide sufficient addressing for each LAN based on the number of hosts required.  
2. **Assigning IP addresses to router interfaces**, using the last usable IP in each subnet for the router.  
3. **Assigning IP addresses to PCs**, using the first usable IP in each subnet and configuring the correct default gateways.  
4. **Configuring static routes** on each router to ensure all PCs across the network could successfully communicate.  

The lab also involved troubleshooting ping failures, verifying connectivity, and understanding how subnet and broadcast addresses affect network communication.

---

## What I Learned

1. **Subnet Calculation**  
   - I learned how to calculate network addresses, broadcast addresses, first and last usable IPs for each subnet.  
   - VLSM allows networks to use IP addresses efficiently by allocating subnet sizes based on the number of hosts needed in each LAN.  
   - Example: LAN3 required 14 hosts, and although a /28 subnet would have sufficed, I chose a /27 for future growth.

2. **Router and PC Configuration**  
   - Assigning the **last usable IP to the router** and **first usable IP to PCs** is a standard practice that ensures consistency and avoids IP conflicts.  
   - Configuring default gateways on PCs ensures they can reach other subnets through the routers.

3. **Static Routing**  
   - I configured static routes on the routers to enable communication across subnets.  
   - Troubleshooting static routes taught me to carefully verify route destinations, next-hop addresses, and subnet masks.

4. **Troubleshooting Connectivity**  
   - Initial ping tests failed due to misconfigured IP addresses and incorrect static routes.  
   - Using commands like `show ip route` helped identify and correct errors.  
   - I learned that subnet broadcast addresses are specific to each subnet, and routers do not forward broadcast messages to other networks.

5. **Network Design Considerations**  
   - Planning for future expansion is important. Choosing slightly larger subnets ensures flexibility without wasting IP addresses.  

---

## Reflection

This lab reinforced the practical application of VLSM and IP addressing in real-world networking scenarios. I gained hands-on experience in:

- Calculating subnets and determining efficient IP allocation.  
- Configuring routers and PCs for proper network connectivity.  
- Implementing static routes to ensure cross-network communication.  
- Diagnosing and fixing common configuration errors.

I now feel more confident in designing and configuring networks using VLSM, understanding the significance of IP planning, and troubleshooting connectivity issues. This lab also highlighted the importance of verification and careful attention to detail, as even a single misconfiguration IP can prevent network communication.

---

## Conclusion

Overall, the VLSM subnetting lab was an excellent exercise in both theoretical understanding and practical implementation. I strengthened my skills in subnetting, router configuration, and troubleshooting, which are essential for efficient network design and management. The experience emphasized the importance of planning, attention to detail, and verification .
