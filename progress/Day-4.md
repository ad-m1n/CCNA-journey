# Day 4: Fundamentals of Ethernet LANs


## Typical SOHO LANs:
- SOHO LAN (Small Office/Home Office Local Area Network): Small-scale network (typically 1–15 devices) used in a home or small business, usually built with a single router/switch combo device that handles routing, switching, DHCP, NAT, and Wi-Fi all in one box.

<p align="center">
    <img src="https://github.com/ad-m1n/CCNA-journey/blob/assets/illus9.png" alt="Day 4-Fundamentals of Ethernet LANs" width="500">
  </p>
  
  <p align="center">
    Illustration on SOHO LANs.
  </p>

## Typical Enterprise LANs:
- Enterprise LAN: Larger-scale network (100s–1000s of devices) built for reliability, security, and scalability, using separate dedicated devices for each function instead of one all-in-one box.

<p align="center">
    <img src="https://github.com/ad-m1n/CCNA-journey/blob/assets/illus10.png" alt="Day 4-Fundamentals of Ethernet LANs" width="500">
  </p>
  
  <p align="center">
    Illustration on OTP and Fiber-optic media.
  </p>

---

## Ethernet Fundamentals:
  ### Physical layer (IEEE 802.3-official set of technical standars definind wired Ethernet LANs):
  - A family of standards under IEEE 802.3, covering speeds from 10Mbps to 400 Gbps.
  - 2 media types carry the signals: 
    - Copper (UTP): Uses electricity
    - Fiber-optic: which uses light and reaches much farther. 

  <p align="center">
    <img src="https://github.com/ad-m1n/CCNA-journey/blob/assets/illus11.png" alt="Day 4-Fundamentals of Ethernet LANs" width="500">
  </p>
  
  <p align="center">
    Illustration on UTP and Fiber-optic media.
  </p>

  ### Data-Link layer:
  - No matter which physical medium is used , the frame format stays the same.
  - This consistency is what lets a switch forward traffic seamlessly between, say, a fiber link and a copper link — the "envelope" wrapping the data never changes shape.
  
  <p align="center">
    <img src="https://github.com/ad-m1n/CCNA-journey/blob/assets/illus12.png?raw=true" alt="Day 4-Fundamentals of Ethernet LANs" width="500">
  </p>
  
  <p align="center">
    Illustration on Data Link Layer Terms.
  </p>
  
  ### UTP (Unshielded Twisted-Pair) Cabling:
  - To send data over copper, you need a closed electrical loop, which is why wires come in pairs. 
  - Twisting each pair cancels out electromagnetic interference (EMI) that would otherwise cause crosstalk between wires.
  - 
  <p align="center">
    <img src="https://github.com/ad-m1n/CCNA-journey/blob/assets/illus13.png" alt="Day 4-Fundamentals of Ethernet LANs" width="500">
  </p>
  
  <p align="center">
    Illustration on UTP cabling.
  </p>

  - Lower speeds (10/100 Mbps) only need 2 of the 4 pairs in the cable; Gigabit speeds use all 4. 
  - Switches often use swappable transceivers instead of fixed ports — GBIC (older, bulky) evolved into SFP (compact, 1 Gbps) and SFP+ (same size, but 10 Gbps).
  
  ### Pinouts:
  - Devices are wired with opposite transmit/receive logic depending on their roles:
    - PCs, routers, and access points: transmit on pins 1&2, receive on 3&6
    - Switches and hubs: transmit on pins 3&6, receive on 1&2
    
    <p align="center">
    <img src="https://github.com/ad-m1n/CCNA-journey/blob/assets/illus133.png" alt="Day 4-Fundamentals of Ethernet LANs" width="500">
  </p>
  
  - This determines the cable types needed:
    - Straight-through cable: connects devices with opposite pin logic (PC to switch). Pins line up directly (1→1, 2→2, etc.).
    - Crossover cable: connects devices with the same pin logic (switch to switch, PC to PC). The transmit pins on one end are crossed to the receive pins on the other.
    - Audio-MDIX: a Gigabit-era feature that detects the wrong cable type and automatically adjusts, so you don't need to worry about which cable to use.
    
    <p align="center">
    <img src="https://github.com/ad-m1n/CCNA-journey/blob/assets/illus14.png" alt="Day 4-Fundamentals of Ethernet LANs" width="500">
  </p>
  
  - Gigabit (1000BASE-T) uses all 4 pairs and sends data both directions on each pair simultaneously, which is more advanced than the older transmit-only/receive-only pair setup.
  - 
    <p align="center">
    <img src="https://github.com/ad-m1n/CCNA-journey/blob/assets/illus1333.png" alt="Day 4-Fundamentals of Ethernet LANs" width="500">
  </p>
  
  ### Fiber Optics:
  - Has glass core (where light travels) surrounded by cladding (which reflects light inward) and protective layers on the outside. There are two types: 
    - Multimode (MMF): larger core, uses cheap LEDs, shorter range (a few hundred meters). Good for connecting equipment within one building.
    - Single-mode (SMF): much smaller core, uses lasers, can travel tens of kilometers, but costs more. Used for long-distance or inter-building links.
    
    <p align="center">
    <img src="https://github.com/ad-m1n/CCNA-journey/blob/assets/illus16.png" alt="Day 4-Fundamentals of Ethernet LANs" width="500">
  </p>
  
## The Ethernet Frame:
  - Preamble + SFD (Start Frame Delimiter): sync the sender and receiver, then signal "the real data starts now"
  - Destination/Source MAC: who it's going to, who it's from
  - Type: tells the receiver what's inside (e.g., IPv4 or IPv6)
  - Data/Pad: the actual payload, padded if too small to meet the minimum size
  - FCS (Frame Check Sequence): a checksum the receiver uses to detect transmission errors
     
    <p align="center">
    <img src="https://github.com/ad-m1n/CCNA-journey/blob/assets/illus17.png" alt="Day 4-Fundamentals of Ethernet LANs" width="500">
  </p>
  
