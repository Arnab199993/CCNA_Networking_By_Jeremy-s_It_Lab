# FTP (File Transfer Protocol) AND TFTP (Trivial File Transfer Protocol)

1. Both of the protocols are used to transfer file over a network.

2. They both use a client server model. 

i. Clients can use FTP or TFTP to copy files from a server. 

ii. . Clients can use FTP or TFTP to copy files to a server.  

# TFTP

1. TFTP was first standardized in 1981.

2. Named Trivial because it is simple and has only basic features compared to FTP. 

i. only allow a client to copy a file to or from a server.

3. It was released after FTP.

4. No authentication (username/pw), so server will respond to all TFTP request.

5. No encryption, so all data sent in plain text.

6. Best used in a controlled environment to transfer small files quickly.

7. TFTP servers listen to UDP port 69.

# TFTP reliability

1. Every TFTP message is acknowledged. 

i. If the client is transferring a file to the server, the server will send ACK messages.

ii. If the server is transferring a file to the client, the client will send ACK messages.

2. Timers are used, and if an expected message isnt received in time, the waiting device will resend the previous message. 

# TFTP Connection

TFTP file transfers have three phases

1. Connection : TFTP client sends a request to the server, and the server responds back, initializing the connection.

2. Data Transfer : The client and server exchange TFTP messages. One sends data and the other sends acknowledgements. 

3. Connection Termination : After the last data message has been sent, a final acknowledgement is sent to terminate the connection. 

# FTP

1. FTP was first standardized in 1971.

2. FTP uses TCP port 20 and 21

3. Username and Password are used for authentication, however there is no encryption. 

4. For greater security FTPS (FTP over SSL/TLS) can be used. (Upgrade to FTP)

5. SSH File Transfer Protocol (SFTP) can also be used greatly for security. (Different Protocol)

6. FTP is more complex than TFTP and allows not only file transfers, but clients can also navigate file directories, add and remove directories, list files etc.

7. The client sends FTP commands to the server to perform these functions. 

# FTP control connection

1. FTP uses 2 types of connections:

i. An FTP control connection (TCP 21) is established and used to send FTP commands and replies. 

ii. When files and data are to be transferred, separate FTP data (TCP 20) connections are established and terminated as needed. 

# Firewall usually dont permit outside devices to initiate connections. In this case, FTP passive mode is used and the client (behind the firewall) initiate the TCP connection.

# File System

A file system is a way of controlling how data is stored and retrieved.

