note: </br>
Major update to OS10.5.3. Last 10.5.2.x backup on folder

# How to use </br>

Tha main point of this space is not the Ansible script, rather the Network configuration and possible replication of it.

Lab includes:

ACCESS</br>
Switch pair with MCLAG </br>
Single Homed Switch</br>
LAG ports for Server attached (host=OS10)</br>
LAG 2x1 and 2x2 links on Leaf1-pair </br>
ACL's/ip-prefix filtering (this is not working due to GNS3)</br>

FABRIC</br>
2X Datacenters room </br>
L3 Fabric with BGP unnumbered </br>
Super-Spine (L3/unnumbered) connection for DC1-DC2 </br>
VxLAN/EVPN overlay (Symetric IRB) - single CP for DC1/DC2 </br>
2x TENANTS, multiple VNI </br>
VRF-route leaking with route-map selective route </br>
Edge Leaf with BGP peering "outside" the fabric for Route type-5 </br>
BFD enable (on Leaf1/Spines-only, to save CPU) </br>
MTU aligned to 9216 all-over-the fabric and hosts </br>

ROUTING</br>
L3 interface towards external router for different VRF for route type 5 termination </br>
L3 VLAN interface for external BGP peering used to "emulate" NSX-T type of attach </br>
L2 exit to Firewall (OS10), FW1/FW2 over VxLAN communication </br>
Static Route for DC1/DC2 exit/last resort Static route redistribution on EVPN for A/A DC exit/fail-over</br>

![image](https://user-images.githubusercontent.com/20860769/142396953-bd7af62a-9a1e-4144-a25c-7741ae3da8b3.png)

NOTES:
# ./ Backup.sh 

Please review https://github.com/val3r1o/OS10backupFabric to understand how ./backup works</br>

