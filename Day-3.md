# Day 3-Networking fundamentals: Connections

In today's progression, I learned about network's fundamentals in connections, such as protocols, addressing, and lifecycles.

---

## Addressing:

- IP address: It identifies devices in a network (IPv4: Short, such as 192.168.1.1 while IPv6 is longer hex format)
- Port number: Identifies specific services or application on that device (port 80 = HTTP, 443 = HTTPS and 22 = SSH)
  
  -> Combined both = Socket (192.168.1.1:443)
  
---

## Protocols:

This is what defines how data is formatted, sent and interpreted. 

- IP (Internet Protocol): This one handle routing/addressing for packets across network. Think of it like a subway train route that will help you move to the right destination instead of getting lost in the sea of train stations.
- TCP (Transmission Control Protocol): This is a protocol offers reliable, ordered and secure communication standard for transmitting data packets between applications across the network.
  # Connection lifecycle of TCP:
  - Three-way handshake (explain underneath)
  - Data transfer: Send packets in sequences, each acknowledged. Lost packages are retransmitted.
  - Congestion control: Prevent overwhelming the network itself.
  - Flow control: Prevent sender from overwhelming the receiver.
  - Termination: Four-way handshake using FIN/ACK from both side to close cleanly.

---

 ### Four-way Handshake:

This is how TCP connection is closed gracefully or establishing secure encryption keys on a Wi-Fi network.
    
```text
FIN/ACK--->ACK--->FIN/ACK--->ACK
```
In this process, there are 3 stages: FIN/ACK, ACK, FIN/ACK, ACK

  - FIN/ACK (Finish/Acknowledge): Requests to close its sending direction.
  - ACK (Acknowledge): Acknowledges request and initiator-to-receiver data flow ends.
  - FIN/ACK (Finish/Acknowledge): Sends termination request once its own pending data finish sending.
  - ACK (Acknowledge): Acknowledges request; connection fully closes on both ends.
 
<p align="center">
  <img src="https://github.com/ad-m1n/CCNA-journey/blob/main/illus4.png" alt="Day 3-Networking fundamentals: Connections" width="500">
</p>

<p align="center">
  Illustration on how the Four-way Handshake operates.
</p>

- WPA2/WPA3 Authentication-Wifi Security:
  
    - In wireless networking, the 4-way handshake confirms that both the client device and the Access Point (AP) know the Wi-Fi password without ever sending the password over the air.
      
       - Message 1 (AP to Client): AP sends a random value (ANonce) to the client.
  
       - Message 2 (Client to AP): Client generates its own random value (SNonce), derives the temporary encryption key, and sends SNonce back alongside a cryptographic signature (MIC).
  
       - Message 3 (AP to Client): AP verifies the signature, derives the encryption key, and sends the network's group key (GTK).

        - Message 4 (Client to AP): Client confirms key installation, establishing an encrypted link.

<p align="center">
  <img src="https://github.com/ad-m1n/CCNA-journey/blob/main/illus5.png" alt="Day 3-Networking fundamentals: Connections" width="500">
</p>

<p align="center">
  Illustration on WPA3 vs WPA2 vs WPA vs WEP.
</p>

### The Three-way Handshake (TCP set up process):
    
```text
SYN--->SYN-ACK--->ACK
```


In this process, there are 3 stages: SYN, SYN-ACK and ACK

- SYN (Synchronize): The client send a request to server, with a syn flag set and a randomly generated sequence number. This action is for requesting a new connection and establish the client's sequence number.
- SYN-ACK (Synchronize-Acknowledge): This will be send from the server side, when it receive the request with both SYN and ACK flag set, which is acknowledging the sequence number of the client, while generate itself its own sequence number. This stage will confirm the request from the client as well as the request to synchronize server's data flow.
  - ACK (Acknowledge): Client send a final packet with ACK flag set, acknowledging the server's sequence number. This final progress will establish the connection set state of both devices.
      

  <p align="center">
  <img src="https://github.com/ad-m1n/CCNA-journey/blob/main/illus1.png" alt="Day 3-Networking fundamentals: Connections" width="500">
</p>

<p align="center">
  Illustration on how the Three-way Handshake operates.
</p>

  Combine TCP and IP, they form the TCP/IP suite, which is the foundation of modern internet.

- UDP (User Datagram Protocol): Skip the Three-way handshake entirely. Connectionless, transmit data immediately without checking if the recipient is ready, or pre-establish a session.
  
  It sends data directly through packets (or datagrams) to destination IP and port with zero delay through "Fire-and-Forget" protocol.
  
  If a packet is lost, corrupted or arrives out of order, it doesn't detect or retransmit, leaving the problem to the application layer. Unlike TCP (20-60 bytes), UDP only needs 8 bytes, so it saves up bandwidth and processing power.

  
  <p align="center">
    <img src="https://github.com/ad-m1n/CCNA-journey/blob/main/illus2.png" alt="Day 3-Networking fundamentals: Connections" width="500">
  </p>

  <p align="center">
  Illustration on how the Fire-and-Forget delivery stands different compare to TCP's Three-way handshake.
  </p>

- Application-layer protocol: defines the rules, message formats, and data structures (like JSON or HTML) software uses to communicate, using underlying TCP or UDP connections to handle raw network delivery.
  
  - Core Functions:

    Data Formatting: Converts raw bytes into structured data (web pages, commands, files).

    Communication Rules: Dictates request types ( GET, POST), response codes ( 200 OK, 404), and message boundaries.

    Application State: Manages user authentication, sessions, and protocol-specific errors independently of the underlying network.

  <p align="center">
    <img src="https://github.com/ad-m1n/CCNA-journey/blob/main/illus3.png" alt="Day 3-Networking fundamentals: Connections" width="500">
  </p>
  <p align="center">
   Application-layer protocol.
  </p>

  - API (Application Programming Interface): is a set of defined rules and protocols that allows different software applications to communicate and share data with each other. Acts as an intermediary, taking a request from one system, delivering it to a target system, and returning the response.
    
  - REST API (Representational State Transfer Application Programming Interface): a standardized architectural style that lets different software applications exchange data over HTTP.
    
    - It uses standard HTTP operations to perform actions on resources:

      GET: Retrieve data (e.g., fetch a user profile).

      POST: Send new data (e.g., submit a form).

      PUT / PATCH: Update existing data.

      DELETE: Remove data.

---

## The OSI Model (7 layers) concept:

  - Physical – cables, signals
  - Data Link – MAC addresses, switches
  - Network – IP addresses, routing
  - Transport – TCP/UDP, ports
  - Session – managing connections/sessions
  - Presentation – encryption, data formatting
  - Application – HTTP, FTP, DNS, etc.

     <p align="center">
    <img src="https://github.com/ad-m1n/CCNA-journey/blob/main/illus6.png" alt="Day 3-Networking fundamentals: Connections" width="500">
  </p>
  <p align="center">
   The OSI Model.
  </p>

---

## Performance Metrics:

  - Bandwidth – max data capacity of a connection
  - Latency – delay between sending and receiving
  - Throughput – actual data transferred over time
  - Jitter – variation in latency (critical for real-time apps)
  - Packet loss – data that fails to arrive
  - 
---

## Security layer:

- TLS (Transport Layer Security), the modern successor to SSL—sits directly between the Transport Layer (TCP) and the Application Layer. It encrypts plain text data (like HTTP) into unreadable cipher text (creating HTTPS) before network transmission.
    - TLS/SSL: encrypts connections (HTTPS = HTTP + TLS)
- Firewalls: filter traffic based on rules.
- VPNs: create encrypted tunnels between networks.

```text
Application Layer(HTTP, SMTP, FTP or Raw Data)<---Security layer(Encryption, Authentication, Integrity)<---Transport layer (TCP-Reliable Delivery)
```

---

### The TSL Handshake:

  Immediately after the TCP 3-way handshake finishes, the TLS handshake negotiates encryption parameters.

   <p align="center">
    <img src="https://github.com/ad-m1n/CCNA-journey/blob/main/illus7.png" alt="Day 3-Networking fundamentals: Connections" width="500">
  </p>
  <p align="center">
   The TSL Handshake.
  </p>

---

### TSL/SSL:

  Encrypts specific application traffic (e.g., HTTPS)

 <p align="center">
    <img src="https://github.com/ad-m1n/CCNA-journey/blob/main/illus8.png" alt="Day 3-Networking fundamentals: Connections" width="500">
  </p>
  <p align="center">
   The TSL/SSL concept.
  </p>

---

### Firewalls:

  Filters network traffic based on security rules.

---

### VPNs:

Encrypts all device traffic and masks IP address

---
