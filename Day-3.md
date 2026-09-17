# Day 3-Networking fundamentals: Connections

In today's progression, I learned about network's fundamentals in connections, such as protocols, addressing, and lifecycles.

## Addressing:

- IP address: It identifies devices in a network (IPv4: Short, such as 192.168.1.1 while IPv6 is longer hex format)
- Port number: Identifies specific services or application on that device (port 80 = HTTP, 443 = HTTPS and 22 = SSH)
-> Combined both = Socket (192.168.1.1:443)
  
---

## Protocols:

This is what defines how data is formatted, sent and interpreted. 

- IP (Internet Protocol): This one handle routing/addressing for packets across network. Think of it like a subway train route that will help you move to the right destination instead of getting lost in the sea of train stations.
- TCP (Transmission Control Protocol): This is a protocol offers reliable, ordered and secure communication standard for transmitting data packets between applications across the network.

### The Three-way Handshake (TCP set up process):
    
```text
SYN--->SYN-ACK--->ACK
```


In this process, there are 3 stages: SYN, SYN-ACK and ACK

- SYN (Synchronize): The client send a request to server, with a syn flag set and a randomly generated sequence number. This action is for requesting a new connection and establish the client's sequence number.
- SYN-ACK (Synchronize-Acknowledge): This will be send from the server side, when it receive the request with both SYN and ACK flag set, which is acknowledging the sequence number of the client, while generate itself its own sequence number. This stage will confirm the request from the client as well as the request to synchronize server's data flow.
  - ACK (Acknowledge): Client send a final packet with ACK flag set, acknowledging the server's sequence number. This final progress will establish the connection set state of both devices.
      

  <p align="center">
  <img src="https://github.com/ad-m1n/CCNA-journey/blob/main/10-2.png" alt="Day 3-Networking fundamentals: Connections" width="500">
</p>

<p align="center">
  Illustration on how the Three-way Handshake operates.
</p>

  Combine TCP and IP, they form the TCP/IP suite, which is the foundation of modern internet.

- UDP (User Datagram Protocol): Skip the Three-way handshake entirely. Connectionless, transmit data immediately without checking if the recipient is ready, or pre-establish a session.
  
  It sends data directly through packets (or datagrams) to destination IP and port with zero delay through "Fire-and-Forget" protocol.
  
  If a packet is lost, corrupted or arrives out of order, it doesn't detect or retransmit, leaving the problem to the application layer. Unlike TCP (20-60 bytes), UDP only needs 8 bytes, so it saves up bandwidth and processing power.

  
  <p align="center">
    <img src="https://github.com/ad-m1n/CCNA-journey/blob/main/10-2.png" alt="Day 3-Networking fundamentals: Connections" width="500">
  </p>

  <p align="center">
  Illustration on how the Fire-and-Forget delivery stands different compare to TCP's Three-way handshake.
  </p>

- Application-layer protocol: defines the rules, message formats, and data structures (like JSON or HTML) software uses to communicate, using underlying TCP or UDP connections to handle raw network delivery.
  
  -Core Functions:

    Data Formatting: Converts raw bytes into structured data (web pages, commands, files).

    Communication Rules: Dictates request types ( GET, POST), response codes ( 200 OK, 404), and message boundaries.

    Application State: Manages user authentication, sessions, and protocol-specific errors independently of the underlying network.

  <p align="center">
    <img src=" " alt="Day 3-Networking fundamentals: Connections" width="500">
  </p>
  <p align="center">
   Application-layer purposes in protocols.
  </p>
