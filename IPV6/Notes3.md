# IPV6 header - Version

1. Length - 4 bits
2. Indicate the version of IP that is used
3. Fixed value of 6 (0b0110) to indicate IPV6.

# IPV6 header - Traffic Class

1. Length 8 bits
2. Used for Qos (Quality of Service), to indicate high priority traffic
3. For example Ip phone traffic, live video calls, etc, will have a traffic class value which gives them priority over other traffic. 

# IPV6 header - Flow Label

1. Length 20 bits. 
2. Used to identify specific traffic flows (communication between a specific source and destination)

# IPV6 header - Payload Length

1. Length 16 bits
2. Indicates the length of the payload (the encapsulated Layer 4 segments) in bytes.
3. The length of the IPV6 header itself isnt included, because its always 40 bytes.


# IPV6 header - Next Header

1. Length 8 bytes
2. Indicates the type of next header (header of encapsulated segment), for example TCP or UDP.

# IPV6 header - Hop Limit

1. Length 8 bits
2. The value in this field is decremented by 1 by each router that forwards it. If it reaches 0, the packet is discarded.


# IPV6 header - Source Destination

1. Length 128 bits each
2. These fields contain the IPV6 addresses of the packet's source and the packets intended destination. 

# NDP : Neighbour Discovery Protocol

NDP is used to replace ARP for IPV6.

The ARP like functions of NDP uses ICMPV6 and solicited node multicast address to learn MAC address of other hosts.

Two message types are uses :

1. Neighbour Solicitation (NS) = ICMPV6 Type 135
2. Neighbour Advertisement (NA) = ICMPV6 Type 136


A computer first sends a **Router Solicitation** message to the "All-Routers" multicast address to announce its presence and ask for network information.
The local router hears this and responds with a **Router Advertisement** that provides the network prefix, the hop limit, and instructions on whether the computer should use DHCPv6 or auto-configuration.
Once the computer generates its own IPv6 address, it performs **Duplicate Address Detection** by sending a **Neighbor Solicitation** to its own new address to ensure no other device is already using it.
When that computer wants to send data to a specific neighbor, it sends a **Neighbor Solicitation** to a special multicast address asking for that neighbor's hardware MAC address.
The target neighbor receives this request and sends back a **Neighbor Advertisement** containing its MAC address, which effectively replaces the job that ARP used to do in IPv4.
Both devices then store this mapping in a **Neighbor Cache** so they don't have to ask for the same information again for a set period of time.
The router continues to send periodic **Router Advertisements** to the entire network to confirm it is still alive and to update any changes to the network prefix or DNS settings.
If a device is moving traffic through a sub-optimal path, the router can send a **Redirect** message to tell that device there is a better first-hop router available on the local link.

IPV6 doesnt use ARP table it uses IPV6 neighbour table.

Another functions of NDP allow hosts to automatically discover routers on the local network

Two messages are used in this process

1. Router Solicitation (RS) = ICMPV6 Type 133
-> Send to multicast address FF02:2 (all routers)
-> Asks all routers on the local link to identify themselves.
-> Sent when an interface is enabled/host is connected to the network

2. Router Advertisement (RA) = ICMPV6 Type 134
-> Send to multicast address FF02.::.1 (all nodes)
-> The router announces its presence , as well as other information about the link.
-> These messages are sent in response to RS messages.
-> They are also sent periodically, even if the router hasn't received an RS. 


# SLAAC (Stateless Address Auto Configuration)

1. Hosts use the RS/RA messages to learn the IPV6 prefix of the local link (ie . 2001:db8::/64), and then automatically generate an IPV6 address. 

2. Using the ipv6 address prefix/prefix-length eui 64 command, you need to manually enter the prefix. 

3. Using the ipv6 address autoconfig command, you dont need to enter the prefix. The device uses NDP to learn the prefix used on the local link. 

4. The device will use EUI 64 to generate the interface id, or it will be randomly generated (depending on the device/maker)

# Duplicate Address Detection (DAD)

DAD allows hosts to check if other devices on the local link are using the same IPV6 address.

DAD uses two messages NS and NA

The host will send an NS to its own IPV6 address. If it does not get a reply, it knows the address is unique. 

If it gets a reply, it means another host on the network is already using the address. 