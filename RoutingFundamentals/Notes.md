# What is routing?

Ans: Routing is the process that routers use to determine the path that ip packets should over a network to reach their destination. Routers store routes to all of their known destination in a routing table. When routers receive packets, they look in the routing table to find the best route to forward the packet.

# Routing methods

There are routing methods (methods that routers use to learn routes)

1. Dynamic Routing : Routers use dynamic routing protocols (ie: OSPF) to share routing information with each other automatically and build their routing tables.

2. Static routing: A network engineer manually configures routes on the router.

A route tells the router : to send a packet to destination X. You should send the packet to next-hop Y.
Next Hop : The next router in the path to the destination. Or if the destination is directly connected to the router, send the packet directly to the destination. Of if the destination is the routers own ip address, receive the packet for yourself (dont forward it).

# Swiches have mac address table and router has routing table.

There are 4 routers connected together and they represent a WAN.

# WAN (Wide Area Network)

A network that extends over a large geographical area.

# In 192.168.1.0/24 the subnet mask is 255.255.255.0. The first 24 bits of octates are all 1 so all of them are 255. These bits are fixed and cant be changed. However the last 8 bit octet are not fixed and can be any number.

A route matches a packets destination if the packets destination ip address is part of the network specified in the route.
Most specific matching route = the matching route with longest prefix length.
If router does not have a packet destination it will drop the packet.
