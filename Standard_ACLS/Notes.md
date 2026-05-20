# ACL (Access Control List)

ACL's have multiple uses.

ACL functions as a packet filter, instructing the router to permit or discard specific traffic. 

ACL can filter traffic based on the source/destination ip address, source/destination layer 4 ports, etc. 

A maximum of one ACL can be applied to a single interface per direction. 

Inbound : Maximum one ACL.

Outbound : Maximum one ACL.

# ACL Types

1. Standard ACL : Match based on Source Ip only

-> Standard Numbered ACLs

-> Standard Named ACLs

2. Extended ACL : Match based on Source/Destination IP, Source/Destination port, etc.

-> Extended Numbered ACLs

-> Extended Named ACLs


# Standard ACLs

Standard ACLs match traffic based on the source ip address of the packet. Standard ACLs are quite simple. Router doesnt check the destination ip, the source layer 4 port, the destination port etc. It just looks at the source ip address of the packet decides to forward or block it. 

Numbered ACLs are identified with a number. (ie ACL 1, ACL 2 etc).

Different types of ACLS have a different range of numbers that can be used. 
-> Standard ACLs can use 1-99 and 1300-1999.

Standard ACLs should be applied as close to the destination as possible.

# Standard Names ACLs

Standard ACLs match traffic based only on the source ip address of the packet.

Named ACLS are identified with a name (ie. 'BLOCK_BOB')

Standard named ACLs are configured by "Standard named ACL config mode" and the configuring each entry within that config mode. 



