OSPF stands for open shortest path first.

Uses the shortest path first algorithm of dutch computer scientist Edsgaer Dijkstra (aka Dijkstras algorithm) 

These versions 

1. OSPFv1 (1989) : OLD, not in use anymore.

2. OSPFv2 (1998) : Used in ipv4

3. OSPFV3 (2008) : Used in ipv6 (can also be used for ipv4, but usually v2 is used)

Routers store information about the network in LSAs (Link State Advertisements), which are organized in a structure called LSDB (Link State Database)

Routers will flood LSAs until all routers in the OSPF area develop the same map of the network (LSDB).

An area is a set of routers and links that shares the same LSDB. 
The backbone area is an area that all other areas must connect to.
Routers with all interfaces in the same area called interal routers.
Routers with interfaces in multiple areas called area border routers (ABR)


OSPF neighbour requirements

Area number must match to be an OSPF neighbour
Interfaces must be in the same subnet
OSPF process must not be shutdown
OSPF Router Id must be unique
Hello and dead timers must match
Authentication setting must match
IP MTU settings must match
OSPF network type must match
