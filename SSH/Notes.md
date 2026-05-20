# SSH

SSH is a protocol used to connect to devices and configure them via CLI. One option to connect to a device and configure it is via the console port. 

SSH was created to solve this by wrapping your entire session in a layer of strong encryption. SSH is the "umbilical cord" that lets you control your hardware without being physically near it.

# Layer 2 switch

1. Layer 2 switches don't perform packet routing and dont build a routing table. They aren't ip routing aware. 

2. However, you can assign an ip address to an SVI to allow remote connections to the CLI of the switch (usually TELNET or SSH)

# TELNET

1. Telnet (Teletype Network) is a protocol used to remotely access the CLI of a remote host.

2. Telnet was developed in 1969.

3. Telnet has been largely replaced by SSH, which is more secure.

4. Telnet sends data in plain text. No encryption.

# SSH

1. SSH (Secure Shell) was developed in 1995 to replace less secure protocols like Telnet.

In computing, a shell is a computer program which exposes an operating system's services to a human user or other program. In general, operating system shells use either a command line interface (CLI) or graphical user interface (GUI), depending on a computers role and particular operation. It is named a shell because it is the outermost layer around the operating system. 

2. SSHV2, a major version of SSHV1, was released in 2006.

3. If a device supports both version 1 and version 2, it is said to run version 1.99.

4. Provides security feature such as data encryption and authentication. 

# SSH configuration : RSA keys

1. To enable and use SSH, you must generate and RSA public and private key pair

2. The keys are used for data encryption/decryption, authentication etc.





