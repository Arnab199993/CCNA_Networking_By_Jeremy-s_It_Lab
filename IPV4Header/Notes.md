# Identifies the version of IP used (*****)
1. IPV4 = 4 (0100)
2. IPV5 = Experimental. (Ethernet Stream Protocol)
3. IPV4 = 6 (0110)
IPV4 length 4 bits
# Internet Header Length (IHL). This field is the half of the octet (4 bits) (*****)

1. The final field of the IPV4 header (Optional) is variable in length, so this field indicate the total length of header.

2. Identifies the length of the header in 4-bytes increment.
Value of 5 = 5 * 4 bytes = 20 bytes

Minimum value is 5. (20 bytes)
Maximum value is 15. (15 * 4 = 60 bytes)
1111 = 1*8 + 1*4+ 1*2 + 1*1 = 15 

The maximum length of ipv4 packet is 65535

If the packet is fragmented due to being too large, this field is used to identify which packet the fragment belongs to.

Minimum IPV4 header length = 20 bytes.
Maximum I4V4 header length = 60 bytes.

# DSCP Field (Differentiated Services Code Point)
Length : 6 bits.
1. Used for Qos (Quality of services)
2. Used to prioritize delay-sensitive data (streaming voice,video etc)

# ECN Field (Explicit Congestion Notification) 
Length : 2 bits
1. Provides end to end (between 2 endpoints) notification of congeston network without dropping packets.
2. Optional fields that requires both endpoints, as well as underlying network infrastructure to support it.

# Total Length Field
Length : 16 bits (2 octets)

1. Indicates the total length of the packet (L3 header + L4 segment)
2. Measured in bytes (not 4-byte increments like IHL)
3. Minimum value of 20 (=IPV4 header with no encapsulated data)
4. Maximum value of 65,365 (maximum 16 bit value)


# IPV4 header. Identification field
1. If a packet is being fragmented due to being too large, this field is used to identify which packet 
the fragments belongs to. So it can be reassembled again with the original packet.
2. All fragments of the same packet will have their own IPV4 header with the same value in this field.
3. Packets are fragmented if its larger than MTU.(Maximum Transmisiion Unit)

# IPV4 header - Identification field
1. The MTU is usually 1500 byte.
2. Remember the maximum size of an Ethernet Frame.
3. Fragments are reassmebled by the recieving host.


# IPV4 header flags field
1. Used to control identify fragments.
2. Length 3 bits
3. Bit 0: Reserved always set to 0.
4. Bit 1 : Dont fragment (DF bit),used to indicate a packet that should not be fragmented.
5. Bit 2 : More fragments (MF bit), set to 1 if there are more fragments in the packet, set to 0 for the last fragment.
6. Unfragmented packets will always have their MF bit set to 0.

# Fragment offset field
1. Length 13 bit.
2. Used to indicate the position of the fragment within the original, unfragmented IP packet.

# Time to leave field (*****)
1. Length : 8 bit.
2. A router will drop a packet with a TTL of 0.
3. Used to prevent infinite loops
4. Originally designed to indicate the packets maximum lifetime in seconds.
5. In practice, indicated a hop count. Each time the packet arrives at a router, the router decreases the TTL by 1.
6. The current recommended default TTL is 64

# Protocol field (*****)
1. Length : 8 bits
2. Indicates the protocol of the encapsulated L4PDU 
3. Value of 6 : TCP
4. Value of 17 : UDP
5. Value of 1 : ICMP
6. Value of 89 : OSPF (dynamic routing protocol)

# IPV4 header - header checksum field (*****)
1. Length : 16 bits
2. A calculated checksum used to check for errors in the IPV4 header.
3. When a router recieves a packet, it calculates the checksum of the header and compares it to the one in this field of the header.
4. If they do not match, the router drops the packet.
5. Used to check errors only in the IPV4 header.
6. IP relies on the encapsulated protocol to detect errors in the encapsulated data.
7.Both TCP and UDP have their own checksum fields to detect errors in the encapsulated data.

# IPV4 header - source/destination ip address field (*****)
1. Length: 32 bits.
2. The source IP address = IPV4 address of the sender of the packet.
3. Destination IP address = IPV4 address of the intended reciever of the packet.

# Options Field
Length : 0-320 bits
1. Rarely Used
2. If the IHL field is greater than 5, it means the options are present.




