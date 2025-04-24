TCP/IP stands for Transmission Control Protocol & Internet Protocol and is a suite of communication protocols used to interconnect network devices on the internet.

It specifies how data should be transmitted over the internet by providing end-to-end communications that identify how it should be broken into packets, addressed, transmitted, routed & received at the destination. 

TCP/IP operates at 4 layers of the OSI Model:
1) Application Layer - Web Applications interacting with the network.
2) Transport Layer - Ensures reliable data delivery & error correction.
3) Internet Layer - Handles addressing & routing of data packets.
4) Network Access Layer - Manages physical transmission of data over the network.

### Differences between TCP & IP

| Feature  | TCP                                                                                | IP                                                                               |
| -------- | ---------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Purpose  | Ensures reliable, ordered and error-checked delivery of data between applications. | Provides addressing and routing packets across networks.                         |
| Function | Manages data transmission between devices, ensuring data integrity & order.        | Routes packets of data from the source to the destination based on IP addresses. |

### How does TCP/IP work?
1) At the application layer, when the user initiates a request, that request is formatted into a protocol-specific format (HTTP for web browsing, SMTP for Email)

2) That request is then broken into small segments in the transport layer whose headers contain:
	- Source Port - The port number of the sending application.
	- Destination Port - The port number of the receiving application.
	- Sequence Number - Ensures segment are re-assembled in the correct order.
	- Checksum - Ensures data integrity.
	Then, either TCP(Transmission Control Protocol) or UDP(User Datagram Protocol) is used for reliable, connection oriented or faster, connection-less communication respectively.
	
3) The Internet Layer then encapsulates the segments into packets containing the following in their header:
	 - Source IP Address - The IP address of the sending computer.
	 - Destination IP Address - The IP address of receiving computer.
	 - Protocol - Indicates whether the packet is TCP or UDP.
	 It then determines the best path for the packet to reach the destination using routing.
	 
4) The Network Access Layer receives the packets and encapsulates them into frames whose headers contain:
	- Source MAC address - The physical address of the sending device.
	- Destination MAC address - The physical address of the next hop (e.g a router from the sender).
	- Error Detection - Ensures data integrity during transmission.

5) At the receiver's end, the reverse of the above steps is performed.

### Mechanism Of Network Access Layer
In practice, the TCP/IP model glosses over what exactly happens when a packet gets transmitted over the internet and this concept will be invaluable when hosting web servers.

1) When the frame leaves the sender's computer, it gets transmitted to their router according to their destination MAC address which contains the MAC address of the default gateway (router).
2) The router then extracts the packet from the frame by stripping away the metadata for the packet and then inspects the destination IP address of the packet.
3) The router uses its routing table & routing protocols to determine the best path for the packet to reach its destination and encapsulates the packet into a new frame with the new destination MAC address.
4) A similar process repeats along the way until the packet reaches the destination router.
5) The router at the destination then decapsulates the frame, checks whether the destination IP address is for a device on its local network and performs ARP (Address Resolution Protocol) to determine the MAC address of the destination device.

#### How does the sender specify the destination IP address of the receiver when the actual IP address of the receiver is hidden behind NAT?
In NAT (Network Address Translation), the destination IP address of the receiver's device is hidden as a private IP address. Therefore, if the destination IP address is not sufficient to identify the device within the network since the sender will have no idea about the private IP address of the receiver in the first place.

What actually happens is that the public IP address of the router is used instead alongside the destination port. The router on the receiver's side will use the destination port to identify the device to forward the packet to.

Hence, this is why port forwarding is a required step for setting up web servers.