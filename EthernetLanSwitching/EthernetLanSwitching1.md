1. Ethernet Head encapsulated with packet with Header and Trailer.
   Header on the left and Trailer on the right
2. The Ethernet Header has 5 fields.
   i. Preamble
   ii. SFD
   iii. Destination
   iv. Source
   V. Type. It indicates the layer 3 protocol encapsulated in the packet which is almost internet protocol IPV4 (V4 means version 4) or IPV6 (V6 means version 6).
   However this is a length field which indicates that length of the encapsulated data depending on the version of the internet.
3. The Ethernet Trailer has only one field that is called FCS.
   FCS Stands for frame check sequence. It is used by recieving device to detect that any errors might have ocuured in transmission.

4. Preamble.
   Features:
   i. Its 7 bytes long. (8 bits = 1 byte so 7 bytes means 56 bits)
   ii. Its a series of alternative 1's and 0's. Which is 10101010 \* 7
   iii. It allows device to synchronize their reciever clocks. To make sure they are ready to recieve the rest of the frame and data inside.

5. SFD
   Feature:
   i. It stands for Start Frame Delimeter.
   ii. Its length is 1 byte (8 bits)
   iii. Its bit pattern is 10101011

6. Destination
   Feature:
   i. It indicates that device sending and recieving the frame.
   ii. It consists of the destination and source MAC address.
   iii. MAC stands for Media Access Device
   iv. MAC size is 6 byte (48-bit) address of the physical device.
   MAC address is separate from logical address (IP address). MAC address is assigned to the device when its made.

7. Type or Length
   i. It has 2 bytes of 16 bits of length. It might be represent as type or length of the encapsulated packet.
   ii. A value of 1500 or less in this field indicated the "LENGTH" of the encapsulated packet in bytes.
   iii. A value of 1536 or greater in this field indicated the "TYPE" of encapsulated packet (usually IPV4 or IPV6) and the length is determined by other methods.
   IPV4 = 0X0800 (Hexadecimal) which is 2048 in decimal.
   IPV6 = 0X86DD (Hexadecimal) which is 34525 in decimal.
   ARP = 0X0806
   MAC address is represented in hexadecimal.

8. Preamble -> 7 bytes
   SFD -> 1 byte
   Destination -> 6 byte
   Source -> 6 bytes (as Destination and Source both are mac addresses)
   Type -> And types of length field is 2 bytes

9. The Ethernet Header has 1 field.
   FCS (Frame Check Sequence)
   4 bytes (32 bits) in length
   Its purpose to detect corrupted data by running a "CRC" algorithm over the recieved data.
   CRC means Cyclic Redundancy Check
10. Ethernet frame in byte - 7,1,6,6,2,4 (From preamble to FCS)

11. MAC Address
    6 byte (48-bit) physical address assigned to the device when it is made
    A.K.A burned in Address
    MAC address in globally uniqe
    The first 3 MAC address are OUI (Organizationally Unique Identifier), which is assigned to the company making the device.
    The last 3 bytes are unique to the devices itself.
    written as 12 Hexadecimal Characters.

12. The decimal system has 10 possible digits : 0,1,2,3,4,5,6,7,8,9
    The 9 represents 9 times 1
13. The hexadecimal represents 16 possible digits: 0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F
14. Unicast frame : A frame destined for a single target(PC2 in this case)
15. Unicast frame : A frame doesnt have an entry to the MAC address table.
16. Known unicast frame : A known unicast frame is a network frame sent to a specific, known MAC address (not broadcast or multicast), where the destination device is identified and reachable on the network.
17. Flodd : Flooding occurs when a network switch doesn't know the destination MAC address, so it sends the frame out of all ports (except the one it came from) to try and find the correct device.
18. In cisco if the pc doesnt send address for 5 min the mac address will be removed from the table.
