Switches have 24 ports
Text upon switches 10/100/1000 Base-T Ports(1-24)-Ports are auto-MDIX
Switches have RJ-45 Ports. (RJ = Registered Jack)

# What is Ethernet?

Ans: Ethernet is a collection of network protocols/standards rather than just a single protocol.

# Example

If one guy speaks english and others japanese then they will not understand each another. So a common language should be there. Thats what ethernet does. It creates a common language between networks.

# Bit

It represents by either 0 or 1.

The connection between devices and networks operates a setSpeed. This speed is measure in bits per second.

# Bytes

Bytes are collection of Bits and

# 8 bits = 1 Byte

If we send data through wire it sends the data in bits. 1 bit every time. It does not go in 1 byte a time. Speed is measured in bits per second.
Data in HDD or SSD measured in bytes per second.

# a gigabyte is 8 times larger than gigabit.

# 1 kilobit = 1000 bits

# 1 megabit = 1,000,000 bits

# 1 gigabit = 1,000,000,000 bits

# 1 terabit = 1,000,000,000,000 bits

# Ethernet Standards (Copper)

1. Defined in the IEEE 802.3 standard in 1983.
2. IEEE = Institute of Electrical and Electronics Engineers.

10 Mbps = {
Common Name : Ethernet
IEEE Standards : 802.3i
Informal Name : 10Base - T
Maximum length : 100m
}

100 Mbps = {
Common Name : Fast Ethernet
IEEE Standards : 802.3u
Informal Name : 100Base - T
Maximum length : 100m
}

1 Gbps = {
Common Name : Gigabit Ethernet
IEEE Standards : 802.3ab
Informal Name : 1000Base - T
Maximum length : 100m
}

10 Gbps = {
Common Name : 10 Gig Ethernet
IEEE Standards : 802.3an
Informal Name : 10GBase - T
Maximum length : 100m
}

# Base stands for Baseband Signalling and T = Twisted Paire

Coper cables in ethernet are UTP cables. UTP stands for Unsheilded Twisted Pair.

<!-- Unsheilded  --> Unsheilded means the wire has no electrical sheild. Which can make them vulnarable to electrical interfierence.
<!--Twisted--> Twisted means wires are twisted. The twist actually protect against electro magnetic interfierence.

So if there are 4 pairs of twisted wires then 8 wires that cable has.

# 10Base - T 100Base - T uses 2 paires (4 wires)

# 1000Base - T 10GBase - T uses uses 4 paires ( 8 wires)

The pc's transmit pin of 1 and 2 is used to transmit data to the switch. (Transmit, TX)
The switch's recieve pins are also 1 and 2 pin used to recieve data from the pc. (Recieve, RX)

The switch's transmits pins are 3 and 6 and it transmits the data from 3 to 6 pin to the pc.
The pc's recieve (RX) pins are also 3 and 6 recieves the data from the switch in its UTP's 3 to 6 pin.

This setup allows for full-duplex transmission, meaning both the PC and the switch can send and receive data simultaneously without a collision.

# Router transmits data in 1 and 2 and recieves in 3 and 6 but switches are opposite.Switches recieves data in 1 and 2 and transmits in 3 and 6.

A copper ethernet has 2 RJ45 connectors one on each end.

In crossoever cable pin 1 connects to pin 3 on the other side and pin 2 connects to pin 6 on the other side.

# Router Transmits : 1 and 2 | recieves : 3 and 6

# Firewall Transmits : 1 and 2 | recieves : 3 and 6

# Pc Transmits : 1 and 2 | recieves : 3 and 6

# Switches recieves : 1 and 2 | Transmits : 3 and 6

Newer networking devices includes a feature called Auto MDIX. Auto MDIX allowes users to automatically detect that which pins their neighbour is transmitting data on and adujust which pin they use to transmit and recieve data

1000Base-T and 10GBase-T both are bidirectional. That means each pair isnt decidated to transmitting or recieving data. Thats why they operate in a much faster speed.

# Fiber optic is the new technology

In those long pin we put SFP Transceiver (Small form factor pluggable). We use fibre optic cable in SFP. And we have 2 connections in fibre optic. One is transfer data and another one is to recieve data.

# 4 parts of firbre optic cable

1. The fibreglass core itself
2. Cladding that reflects light.
3. A protective buffer
4. The outer jacket of the cable

# Types of fibre optic cable

1. Single Mode Fibre
2. Multi mode fibre

In multimode fibre

1. Core diameter is wider than single-mode fibre
2. Allows multiple angles (mode) of light waves to enter the fibreglass core.
3. Allows longer cables than UTP, but shorter cables than single mode fiber.
4. Cheaper than single mode fibre ( due to cheaper led base SFP transmiter).

In singleMode fibre

1. Core diameter is narrower than multimode fibre
2. Light enters as a single angle (mode) from a laser-based transmitter.
3. Allows longer cables than UTP and multimode fiber.
4. More expensive than multi mode fiber ( due to more expensive laser base SFP transmitters).

# FIber optic cable standards

1000Base-LX:{
Informal Name : 1000Base-LX
IIEE Standard : 802.3z
Speed : 1 GBPS
Cable-Type : Multimode or single mode
Maximum Length : 550m (MM) 5km (SM)
}

10GBase-SR:{
Informal Name : 10GBase-SR
IIEE Standard : 802.3ae
Speed : 10 GBPS
Cable-Type : Multimode
Maximum Length : 400m
}

10GBase-LR:{
Informal Name : 10GBase-LR
IIEE Standard : 802.3ae
Speed : 10 GBPS
Cable-Type : Single Mode
Maximum Length : 10 Km
}

10GBase-ER:{
Informal Name : 10GBase-ER
IIEE Standard : 802.3ae
Speed : 10 GBPS
Cable-Type : Single Mode
Maximum Length : 30 Km
}

# Difference between UTP vs Fiber-Optic-Cable

# UTP

1. UTP lower cost than fiber optic
2. Shorter maximum distance than fiber-optic (~ 100m)
3. Can be vulnarable to EMI (Electromagnetic Interferance)
4. RJ45 ports used with UTP are cheaper than SFP ports
5. Emit (Leak) a faint signal out side the cable, which can be copied.(Security Risk)

# Fiber Optic

1. Higher cost than UTP
2. Longer maximum distance than UTP
3. No vulnerability to EMI
4. SFP ports are more expensive than RJ45 ports (Single mode is more expensive than multimode)
5. Does not emit any signal outside of the cable ( = no security risk)
