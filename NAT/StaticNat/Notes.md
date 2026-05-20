# NAT (Network Address Translation)

NAT is used to translate the source and / or destination ip address of a packet to a different ip address.

# Private IPV4 addresses (RFC 1918)

IPV4 doesn't provide enough addresses for all devices that need an ip address in the modern world.

The lon-term solution is to switch to IPV6.

There are three main short term solution 

1. CIDR

2. Private IPV4 addresses 

3. NAT

4. RFC 1918 specifies the following IPV4 address ranges as private:

1. 10.0.0.0/8 (10.0.0.0 to 10.255.255.255) ----> Class A

2. 172.16.0.0/12 (172.16.0.0 to 172.31.255.255) ----> Class B

3. 192.168.0.0/16 (192.168.0.0 to 192.168.255.255) ----> Class C

4. We are free to use these addresses in my network. They dont have to be globally unique.

5. Private IP addresses cannot be used over the internet. Thats where NAT comes in.

If a private IP addresses cant be used over the internet, how can i access the internet from my pc? Thats where NAT comes in. Somewhere accross the internet there is another pc and they have same ip address like mine. If there is packet travelling over the destination with the destination address 192.168.0.167, which pc it will go? My pc or the other one with the same ip address? Without NAT there would be Two problems:

1. Duplicate Address

2. Private IP addresses can't be used over the internet. So the pc's can't access the internet.

NAT solves both the problems for us. Although the PC's and the routers internal interfaces have identical private addresses, perhaps routers external interface has the public ip address 203.0.113.1, and the router has the public ip address 203.0.113.5. Although the private ip addresses are not unique the public ip address must be unique. When the PC needs to reach the destination over the internet, NAT will allow it to borrow the unique public ip address of my router, or another public ip address I have configured for NAT. In fact, not just the pc all other devices in my home can use that same single ip address to access the internet, all at the same time.

# NAT

Network Address Translation (NAT) is used to modify the source and/or destination IP addresses of packets.

There are various reasons to use NAT, but the most common reasons is to allow hosts with private IP addresses to communicate with other hosts over the internet. 

# How NAT works

PC1's IP address is 192.168.0.167 and it wants to communicate with the server 8.8.8.8. So it creates a packet with source IP 192.168.0.167 and destination 8.8.8.8. It sends the packet to its default gateway, R1. This is where NAT happens. R1 translates the source IP address from 192.168.0.167 to 203.0.113.1, the IP address of its external interface.Thats why its called Source NAT because it translates the source IP address. Static NAT doesnt use Routers IP address. It uses a separate address. Router then sends the packet out to the internet and it arrives at its destination 8.8.8.8. Now the server will send a reply. The source is 8.8.8.8 and the destination is 203.0.113.1. It sends the packet to R1 which the reverse the translation. 203.0.113.1 is translated back to 192.168.0.167.

# STATIC NAT (One kind of Source NAT)

1. Static NAT involves statically configuring one-to-one mappings of private IP address to public IP addresses. 

2. An inside local ip address is mapped to an inside global ip address.

i. Inside Local ----> The ip address of inside host, from the perspective of the local network. 

* The ip address actually configured on the inside host, usually a private address. 

ii. Inside Global ----> The IP address of the inside host, from the perspective of outside hosts.

* The ip address of the inside host after NAT, usually a public address.

iii. Outside Local ----> The IP address of the outside host, from the perspective of the local network.

iv. Outside Global ----> The ip address of the outside host, from the perspective of outside network. 

# Static NAT involves statically configuring one-to-one mappings of private IP addresses to public IP addresses.

When traffic from the internal host is sent to the outside network, the router will translate the source address.

However, this one-to-one mapping also allows external hosts to access the internal host via the inside global address.







