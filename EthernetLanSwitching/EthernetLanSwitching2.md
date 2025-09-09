The preamble and sfd is usually not considered part of the ethernet header.
Although it is sent with the every ethernet frame.Therefore the header+trailer is 18 bytes.(6+6+2+4). Only destination,source,type and fcs goes in the ethernet frame.

The minimum size for an ethernet frame (Header + Payload[Packet] + Trailer) is 64 bytes.
64 bytes -18 bytes (header + trailer size) = 46 bytes
Therefore the minimum payload (packet) size is 46 bytes

if the payload is less than 46 bytes, padding bytes are added.

ie 34-byte packet + 12-byte padding = 46 bytes.

# That means a hacker can fill other space padding with malicious content which is less than 46 bytes. This is called Ehterleak.

When i send data to the another computer i enter the ip address not mac address.

When pc 1 sends data to pc 2 it knows its ip adress but dont know its mac adress. To discover the pc 2's mac address pc 1 uses ARP(Address Resolution Protocol)

# ARP

1. ARP stands for address resolution protocol.
2. ARP is used to discover the layer 2 address (MAC address) of a known Layer 3 address (IP address)
3. Consists of two messages:
4. The ARP request sends by device which wants to know the address of other device.
5. The ARP reply which is sent to inform the requesting device of the mac address.

ARP request is broadcast and ARP reply is unicast.

✔️ If a PC knows the IP but not the MAC → it sends an ARP broadcast
✔️ If a switch doesn’t know the MAC’s port → it floods the frame
✔️ Both result in broadcast traffic, but for different reasons and from different devices

# ARP Command

1. Use arp -a to view the ARP table (Windows, macOs, Linux)
2. Internet Address = IP address (Layer 3 address)
3. Physical Address = MAC address (Layer 2 address)
4. Type static = default entry
5. Type dynamic = learned via ARP

Have to change ARP setting in my home router to prevent [Arp_Spoofing] using wireshark.

# Ping

1. A network utility that is used to test reachability
2. Measures round-trip time.(from pc 1 to pc 3 and back to pc 1)
3. Uses two messages
4. Like ARP ping uses 2 messages
   i. ICMP Echo Requesr
   ii. ICMP Echo Reply

5. PC 1 broadcasts the ICMP Echo Request.It is sent to a specific host. So it has to know the MAC address of the destination host which is ARP must be used first.

# Command to use ping : ping (ip-address)

.!!!! = The period (.) indicates a failed ping and exclaimation points (!)indicate successful ping. The first ping failed because it used ARP because pc 1 didnt know pc2's MAC Address.

# Aging

Dynamic mac address is being removed from MAC address table after 5 minuites. This is called aging.
