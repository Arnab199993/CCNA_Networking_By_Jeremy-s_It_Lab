# TCP (Transmission Control Protocol)

Layer 4 provides transparent transfer of data between end hosts.
Provides (or doesn't provide) various services to application.

i. reliable data transfer
ii. error recovery
iii. data sequencing
iv. flow control

Provide layer 4 addressing (port numbers)

i. Identify the application layer protocol.
ii. Session multiplexing

# Pc 1 ---> (TCP) src : 50000 Dst: 80 --> Server 1 (TCP) src : 80 Dst: 50000

# The destination port (80) identifies the application layer protocol (TCP 80 = HTTP). Destination Port identifies the application layer protocol.

# The destination Port is randomly selected by PC 1, helps identify the session.



# Pc 1 ---> (TCP) src : 60000 Dst: 21 --> Server 2 (TCP) src : 21 Dst: 60000

# TCP 21 = FTP (File Transfer Protocol)

The following ranges are designed by IANA (Internation Assigned Numbers Authority)

Well known port numbers : 0 - 1023
Registered port numbers : 1024 - 49151
Ephemeral/private/dynamic port numbers : 49152 - 65535



Transport,Common Ports to Memorize
TCP : "21 (FTP), 22 (SSH), 23 (Telnet), 25 (SMTP), 80 (HTTP), 443 (HTTPS), 445 (SMB), 3389 (RDP)"
UDP : "53 (DNS), 67/68 (DHCP), 161 (SNMP), 500/4500 (VPN traffic)"


# TCP (Transmission Control Protocol)

1. TCP is connection oriented. That means before actually sending data to the destination host, the two hosts communicate to establish a connection. Once the connection is established, the data exchange begins.

2. TCP provides reliable connection.
The destination host must acknowledge that it received each TCP segment.
If a segment isnt acknowleged, it is sent again.

3. TCP provides sequencing
Sequence numbers in the TCP header allow destination hosts to put segments in the correct order even if they arrive out of order.

4. TCP provides flow control.
The destination host can tell the source host to increase / decrease the rate the data is sent.

In TCP Ack,Syn and Fin are used to establish and terminate connection.


# Establishing connection (Three way handshake)

The method TCP uses to establish connection is TCP three way handshake. It has the name because three messages being sent between the two hosts. 

Suppose pc1 wants to establish conncetion with server 1. First it must connect a TCP Connection. To do so it uses these two flags in TCP header. Ack means Acknowledgement and Syn means Sychronization. FIrst Pc 1 will send a TCP segment to server 1 with the syn flag set, meaning that bit is set to 1. That is part 1 of TCP handshake. Next server 1 will reply by sending a TCP segment to pc1 with the SYN and ACK flag set. So both bits are set to 1. That is part 2 of the three way handshake. Finally PC1 will send a TCP segment with ACK bit set. Now the three way handshake is complete and the connection is established. 

Syn (pc 1) -> Syn (server 1), Ack (server 1) -> Ack (pc 1)

# Terminating connection (Four way handshake)
 How TCP terminates connections. This process sometimes is called TCP four way handshake is less famous than three way. When PC 1 realizes when it no longer needs connections with server 1 it will initiate this process to terminate the connection. The process uses these two flags in the TCP header, FIN and ACK. FIrst Pc 1 will send a TCP segment to server 1 with the Fin flag set. Server 1 responds with an ACK. Server 1 then sends its own Fin. Finally pc 1 sends an ACK in response to server 1's Fin, and the connection is terminated.

 Fin (pc 1) -> Ack (server 1) -> Fin (Server 1) -> Ack (pc 1)


# TCP : Sequencing / Acknowledgement

Seq 10 (pc 1, this is three way handshakes syn) -> Seq 50, Ack 11  (pc 2, this is three way handshakes SYN ACK) ->Seq 11, Ack 51 (pc 1, this is three ways handshakes ACK) -> Seq 51, Ack 12 (pc 2) -> seq 12, Ack 52 (pc 1)



# UDP (User Datagram Protocol)

1. UDP is not connection oriented. The sending host does not establish a connection with the destination host before sending data. The data is simply sent.

2. UDP does not provide reliable communication. When UDP is used, acknowledgement are not sent for received segments. If a segment is lost, UDP has no mechanism to transmit it. Segments are sent "best effort". 

3. UDP does not provide sequencing.
There is no sequence number field in the UDP header. If segments arrive out of order, UDP has no mechanism to put them back in the order. 

4. UDP does not provide flow control.
UDP has no mechanism like TCPS window size to control the flow of data. 

# For application the requires reliable communication (for example downloading a file), TCP is preferred.

# For application like real time voice and video, UDP is preferred.


# Port Numbers

1. # TCP : 
FTP data (20), 
FTP Control (21), 
SSH (Secure Shell of routers and switches) (22), 
Telnet (which can also be used to connect to the Cli of devices, uses TCP port 23) (23), 
SMTP (Simple Male Transfer Protocol is used for sending mail and uses port 25) (25)
HTTP (Hyper Text Transfer Protocol commonly used for accessing web pages, uses TCP port) (80)
POP3 (Post Office Protocol 3, uses TCP port 110) (110)
HTTPS (HYper Text Transfer Protocol Secure) (443)

2. # UDP :
DHCP Server (67)
DHCP client (68)
TFTP (The Trvial File Transfer Protocol) (69)
SNMP (Simple Netwok Managing Protocol) agent (161)
SNMP manager (162)
Syslog (514)

3. TCP & UDP
The only protocol that uses both TCP and UDP is DNS (Domain Name Services) (53)
