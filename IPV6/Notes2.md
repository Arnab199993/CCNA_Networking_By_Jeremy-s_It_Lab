# EUI (Extended Unique Identifier)

EUI-64 is a method of converting a MAC address (48 bits) into a 64 bit interface identifier.

This interface identifier can then become the 'host portion' of a /64 IPV6 address. 

# How to convert the MAC address

1. Divide the MAC address in half

1234 5678 90AB -> 1234 56 | 78 90AB

2. Insert FFFE in the middle

1234 56FF FE78 90AB

3. Invert the 7th bit 

1234 56FF FE78 90AB -> 1034 56FF FE78 90AB

2 -> 0010 -> 0000


# Mac Addresses can be divided into 2 types 

1. UAA (Universally Adminstrative Address). Unique assigned to the device by the manufacturer.

2. LAA (Universally Adminstrative Address). Manually assigned by an admin (with the mac address command on the interface) or protocol. Doesn't have to be globally unique.

You can identify a UAA or LAA by the 7th bit of the MAC address, called the  U/L bit (Universal/Local bit)

U/L bit set to 0 = UAA
U/L bit set to 1 = LAA

In the context of IPV6 address/EUI-64, the meaning of U/L is bit reserved 

U/L bit set to 0 = The mac address the EUI-64 interface id was made from was an LAA.
U/L bit set to 1 = The mac address the EUI-64 interface id was made from was an UAA.

# Global unicast address

Originally defined as 2000::/3 block (2000 :: to 3FFF : FFFF : FFFF : FFFF : FFFF : FFFF : FFFF : FFFF)

IPv6 doesn’t use ARP. It uses Neighbor Discovery Protocol (NDP), which runs on ICMPv6.

# Link Local Addresses

Link Local IPV6 addresses are automatically generated on IPV6 enabled interface.


Unicast address is used for one source to one connection. Broadcast addresses are one source to all destination.

Uses the address block FE80 :: /10 (FE80 :: to FEBF : FFFF : FFFF : FFFF : FFFF : FFFF : FFFF : FFFF)

However the standard states that the 54 bits after FE80 / 10 should be all 0, so you wont see link local address beiginning with FE9, FEA or FEB. only FE8.

# Multicast Address


All nodes / hosts (functions like broadcast) => FF02 :: 1 (IPV6) => 224 . 0 . 0 . 1 (IPV4)

All routers   => FF02 :: 2 (IPV6) => 224 . 0 . 0 . 2 (IPV4)

All OSPF routers   => FF02 :: 5 (IPV6) => 224 . 0 . 0 . 5  (IPV4)

All OSPF DRs/BDRs   => FF02 :: 6 (IPV6) => 224 . 0 . 0 . 6 (IPV4)

All RIP routers  => FF02 :: 9 (IPV6) => 224 . 0 . 0 . 9 (IPV4)

All EIGRP routers  => FF02 :: A (IPV6) => 224 . 0 . 0 . 10 (IPV4)

# Multicast address scope

IPV6 defines multiple multicast scopes which indicate how far the packet should be forwarded. 

# IPV6 multicast scopes

1. Interface Local (FF01) : The packet doesnt leave the local device. Can be used to send traffic to a service within the local device. 

2. Link Local (FF02) : The packet remains in the local subnet. Routers will not route the packet between subnets.

3. Site Local (FF05) : The packet can be forwarded by routers. Should be limited to a single physical location. (not forwarded over a WAN)

4. Organization Local (FF08) : Wider in scope than site local (an entire company/organization).

5. Global (FF0E) : No boundaries. Possible to be routed over the internet.

# Anycast

Anycast is a feature of IPV6.

Anycast is one to one of many

# Other IPV6 address

1. :: the unpecified IPV6 address => Can be used when a device doesnt know yet its IPV6 address.

IPV6 default routes are configured to ::/0

IPV4 equivalent 0.0.0.0

2. ::1 => The loopback address => Used to test the protocol slack on the local device.

3. IPV4 equivalent 127.0.0.0/8 address range.
