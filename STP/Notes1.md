# Network Redundancy

Ans: Redundancy is an essential part of network design.
If one network fails then you must ensure that other components will take over with little or no downtime.

# STP prevents Layer 2 loops by placing redundant ports in a blocking state, essentially disabling the interface.

Interfaces in a blocking state only send or receive STP messages (called BPDU's = Bridge Protocol Data Units)

SO switch A sends an arp requests to switch B and B sends it back to A. And they just give and take same packet multiple times and multiply the packets by treating them as new packets. Its called broadcast storm.

By Selecting which ports are forwarding and which ports are blocking, STP creates a single path to/form each point in the network. This prevent layer 2 loops.

Stp eanbled switches send/receive Hello BPDUs out of all interfaces, the default timer is 2 seconds (the switch will send a Hello BPDU out of every interface, once every 2 seconds)

If a switch receives Hello BPDU on an interface, it knows that interface is connected to another switch (routers, pcs, exc, do not use STP. So they do not use HELLO BPDUs).

# Root Bridge

i. Switches use one field in the STP BPDU, the bridge Id field, to elect a root bridge for the network.
ii. The switch with the lowest bridge becomes the root bridge.
iii. All ports on the root bridge are put in a forwarding state, and other switches in the topology must have a path to reach the root bridge.
iv. Bridge id = Bridge Priority (16 bits, by default its 32768) + Mac Address (48 bits)