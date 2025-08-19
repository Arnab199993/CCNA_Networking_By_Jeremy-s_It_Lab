# OSI Model and Tcp/Ip Suite

# what is a networking model?

Ans : Networking models categorize and provide a structure for networking protocols and standards. A networking protocols are a set of rules defining how many devices and software should work.

# OSI Model

1. OSI stands for open system interconnection model
2. A conceptual model that categorizes and standardarizes the different functions in a network
3. Created by the "International organization for standardization" (ISO)
4. Network functions are divided into seven layers
5. These layers work together to make the network work

These layers are
7. Physical Layer
6. Presentation
5. Session
4. Transport
3. Network
2. Data Link
1. Physical 


# 7 Application Layer

1. This layer is closest to the end user
2. Interacts with software applications, for example your web browser (Brave,Firefox,Chrome etc)
3. Http and Https are layer 7 protocols (https://cisco.com)


Functions of layer 7 include
1. Identifying Communicating partners
2. Synchronizing Communication

The software application interacts with layer 7 application layer to layer 1 physical layer and connects with another pc's physical layer. This process is called encapsulation. This data is processed through OSI stack and each layers adds something to the original data. But the time it reaches physical wire its electrical system ona wire sends a signal to the neighbouring system.Then the neighbouring system perfoms an opposite process. The additions of each layers are stipped off until the data reaches the application layer of the neighbouring system. This process is called De-encapsulation. The additional information is removed as the data processed of the stack.

Both En-capsulation and De-capsulation are the processes are examples of json layer example. The communiation between two different application layer interaction is called same layer interaction.

# 6 Presentation Layer

1. Data in the application layer is in application format.
2. It needs to be translated to a different format to be sent over the network.
3. The presentation layer's job is to translate between application and network formats.
4. For example, encryption of data as it is sent, and decryption of data as it is received.
5. Also translates between different application- layer formats.


# 5 Session Layer

1. Controls dalogues (Sessions) between communicating hosts.
2. Establishes, manages, abd terminates connections between local application (for example, your web browser) and the remote application (for example, YouTube)


# 4 Transport Layer

1. Segments and reassembles data for communications between end hosts.
2. Breaks large pieces of data into smaller segments which can be more easily sent over the network and less likely to cause tranmission problems if error occur.
3. Transport layer provides host-to-host communication.

# 3 Network Layer

1. Provides connectivity between end hosts on different networks (ie. outside of the LAN)
2. Provides logical addressing (IP addresses)
3. Provides path selection between source and destination.
4. Routers operate at Layer 3


7,6 and 8 layer and layer 4 header and layer 3 headers combination is called packet.

Next the packet is furthur encapsulated in layer2.

this time packet is = Layer 2 trailer + Data + Layer 4 header + Layer 3 header + Layer 2 header


# 2 Data Link Layer

1. provides node to node connectivity and data transfer ( for example, pc to swtich, switch to router, router to router)
2. Defines how data is formatted for transmission over a physical medium (for example, coppur UTP cables)
3. Detects and (possibly) corrects physical Layer errors.
4. Uses layer 2 addressing, separate from layer 3 addressing
5. Switches operate at layer 2

L2 trailer + Data flows to layer 5 + Layer 4 header added + L3 header added (L4 + L3 = Packet) +  L2 header (L2 trailer + Data + L4 header +L3 header + L2 header = frame)

Data isnt furthur encapsulated at layer 1. The frame is then sent over the connection, whether its electrical signals over a wire or wireless signals in the case of wifi, to the neighboring system.

# 1 Data Link Layer

1. Defines physical characterstics of the medium used to transfer data between devices.
2. For example, voltage levels, maximum transmittion, distances, physical connectors, cable specifications, etc.4
3. Digital bits are converted into electrical (for wired connections) or radio (for wireless connections) signals
4. All of the information in Day 2's video (cables,pin,layouts, etc) is related to physical layer.

The data comes from the applicationn to physical and when it reaches to the neighour device in the network the layer 2 header and trailer are removed in layer 3 network and then layer 3 header are removed in transport leaving only data and layer 4 header and finally layer 4 data is removed and we are left with the only original data prepared by the upper layer of the original device.














