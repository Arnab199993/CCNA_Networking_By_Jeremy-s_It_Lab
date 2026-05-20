1. What is a Trunk Port?
Ans : Where access port belongs to a single VLAN, Trunk port carries traffice with multiple VLAN.
2. 802.1q encapsulation
Ans : It is an additional tag added to an ethernet frame which is used to identify which Vlan taffic belongs to on a trunk

802.1q has been inserted between source and type/length fields of the Ethernet frame

3. VLAN ID. 12 bits in length. Identifies the VLAN the frame belongs to. 
12 bits in length = 4096 (total vlans 2 to the power 12), range of 0- 4095
Vlan 0 and 4095 are reserved and cant be used
Therefore the actual VLAN range is 1 to 4094

so I have 2 options buying multiple switch or splitting the Network for individual department which is VLAN you are saying. Then VLAN also has 2 type one is access port which is for one VLAN (like department) and trunking port which can carry multiple VLAN (like VLAN 10 for hr, VLAN 20 for guests wifi).Access port strip away the VLAN tag before the data hits the computer.

4. The range of VLANS are divided into 2 parts

i. Normal Vlan : 1-1005;
ii. Extended Vlan : 1006 - 4094

# some older device cant use extended vlan range (Cisco Catalyst)

5. 802.1q has a native feature called Native Vlan. (ISL doesnt have this feature). The native VLAN is VLAN 1 by default on all trunk ports, however this can be manually configured in each trunk ports. The switch doesnt add 802.1q tag to frames in the native VLAN.When a switch received an untagged frame on a trunk port, it assumes the frame belong to the native VLAN. It is very important the native VLAN Matches.

The tag has 2 fields
i. tag protocol identifier (TPID)
ii. Tag control information (TCI)
iii. TCI consists of 3 sub fields.(PCP,DEI,VID)
iv. VID is 12 bits long and identies as VLAN no.

6. ROAS is used to router between multiple VLANS using a single interface On the router and a switch. So its just a single path connected with every VLAN (VLAN 10, VLAN 20). The switch interfaces is configured as regular trunk. The router interface is configured using subinterfaces. You configure the VLAN tag and ip address on each subinterfaces.

ii. The router will behave as if frames arriving with a certain VLAN tag  have arrived on the subinterface configured with that VLAN tag.

iii. The router will tag frames sent out of each subinterfaces with the VLAN tag configure on the subinterface.
