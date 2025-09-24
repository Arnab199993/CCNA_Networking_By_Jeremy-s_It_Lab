# Half Duplex : The device can not send and recieve data at the same time. If it is recieving a frame, It must wait before sending a frame.

# Full duplex : The device can send and recieve data at the same time. It does not have to wait.

# Collision Domain

If two devices send at the same time their signals crash into each other (a collision), both stop, wait a bit, and try again. To deal with half duplex and collision ethernet devices uses a mechanism CSMA/CD (career sense multiple access collision detection)

# CSMA/CD

1. Career sense multiple access with collision detection
2. Before sending frames, devices 'listen' to the collision domain until they detect that other devices are not sending.
3. If a collision does occur, the device sends a jamming signal to inform the other devices that a collision happened.
4. Each device will wait a random period of time before sending frames again
5. The process repeats

# Speed/Duplex autonegotiation

1. Interface that can run at different speeds (10/100 or 10/100/1000) have default settings of speed auto and duplex auto.
2. Interfaces advertise their capabilities to the neighboring device, and they negotiate the best speed and duplex setting they are both capable of.
