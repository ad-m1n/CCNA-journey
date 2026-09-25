# Day 2- Simple Topology on cisco packet tracer, learned the basic hardware of network
## Simple topology:
This topology represent connection between two lands:

---

## Land1:

Land 1 represent an office environment, with two office PCs, connected to the local network.

---

## Devices:

- End devices/clients are PC0 and PC1
- One switch Switch0 to distribute connections to end devices
- One router Router 2 to handle internal routing
- One firewall ISA0 for traffic security.

---

### Network design:

Land 1 consist the office PCs connecting to a switch. This switch connect directly to the router, then go through a firewall before reaching the internet. 

Traffic flow:

```text
PC → Switch → Router → Firewall → Internet
```


## Land 2:

Land 2 represent a Data Center with 3 servers to provide services that clients request, probably used to store the office's important data or/and resources.

---

## Devices:

- Three servers Server 0, Server 1 and Server 2
- One switch Switch1 for connection distributing
- One router Router3 for internal routing
- One firewall ISA1 for traffic security

---

### Network design:

Land 2 consist the 3 servers connecting to a switch. This switch connect directly to the router, then go through a firewall before reaching the internet. 

Traffic flow:

```text
Servers → Switch → Router → Firewall → Internet
```

## Inbetween:

The router (The Internet) is represented as a communication path for land 1 and land 2. This external environment also consist another branch connection which is Laptop0.

- Router0 as for The Internet
- External connection: Laptop0

---
## Simple Network Typology:

  <p align="center">
    <img src="https://github.com/ad-m1n/CCNA-journey/blob/main/assets/lab-01.png" alt="Day 02 test" width="1000">
  </p>
  
  <p align="center">
    Simple test of endpoints connection, server and network with external branch connection
  </p>
