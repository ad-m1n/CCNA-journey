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

-   The Three-way Handshake (TCP set up process):
    
    ```text
    SYN--->SYN ACK--->ACK
    ```

  <p align="center">
  <img src=" " alt="Day 3-Networking fundamentals: Connections" width="1000">
</p>

<p align="center">
  Enterprise topology consisting of a New York branch, Tokyo branch, perimeter firewalls, routers, switches, servers, workstations, and an external attacker simulation.
</p>
