# Networking reference architecture

This document describes the current OpenSpot prototype topology: Spot, onboard compute and sensors, the field wireless bridge, and the operator-side network. It is a reference architecture, not yet a validated range or performance specification.

---
## System Layout

![Payload Networking Diagram](../media/Spot-Setup.png)

- **Spot**  
  - GXP port provides power + network.  
  - Example IPs:  
    - `192.168.50.3` (GXP)  
    - `192.168.80.3` ("SpotSpot")  
    - `10.0.0.3` (Management)  

- **Payload switch (2.5 GbE)**
  - Connects Spot, Jetson Orin, Ouster OS-0 sensor, and Ubiquiti Bullet (via PoE injector).  

- **Jetson Orin**  
  - Example IP: `192.168.50.5`.  

- **Ouster OS0 LiDAR**
  - Example IP: `192.168.50.XXX`.  

- **Wireless bridge**
  - Pair of Ubiquiti Bullets with passive PoE.  
  - Extends payload network to the operator side.  

- **Operator side**
  - Router + AP (`192.168.50.1`, SSID: `spotfi-5`).  
  - Steam Deck connects via Wi-Fi (`192.168.50.XXX`).  
  - Powered from external power station (e.g., Jackery).  

---

## Safety and deployment notes

- The diagram contains example addresses. Confirm the actual Spot, payload, and management subnets before connecting equipment.
- The prototype uses passive PoE for the illustrated Ubiquiti radios. Passive PoE is not interchangeable with standards-based 802.3af/at/bt; verify voltage, polarity, connector, and device requirements before energizing a link.
- Add configuration backups, channel/country settings, security configuration, weather protection, strain relief, and a documented recovery path before treating this as a field deployment recipe.
- A wireless bridge is not a safety channel. Motion must transition to a safe state when commands or heartbeats are lost.
- **Color coding in the diagram:**
  - Blue = Network  
  - Red = Power  
  - Red dotted = Passive PoE  
## Validation still required

The public-alpha release does not yet provide repeatable measurements for range, throughput, latency, jitter, packet loss, recovery time, interference, or power consumption. These are tracked in the [release roadmap](roadmap.md).
