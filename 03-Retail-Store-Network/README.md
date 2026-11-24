# Retail Store Network — Design & Implementation

**Platform:** Cisco Packet Tracer  
**Project type:** Independent network design and implementation project

## Overview
This project documents a simulated retail-store network supporting front-of-store checkout operations, self-checkout, guest wireless access, back-office workstations, printing, management access, and connectivity to an external payment server.

The physical design includes FRONT-STORE and BACK-STORE Cisco 2960 access switches, an L3-SW1 Cisco 3560 multilayer switch, EDGE-R1 and ISP-R1 Cisco 2911 routers, a wireless access point, printer, client endpoints, and an external payment server.

## Network segmentation
| VLAN | Purpose | Subnet / gateway |
|---:|---|---|
| 10 | POS | 192.168.10.0/24 — 192.168.10.1 |
| 20 | Self-checkout | 192.168.20.0/24 — 192.168.20.1 |
| 30 | Back office | 192.168.30.0/24 — 192.168.30.1 |
| 40 | Guest Wi-Fi | 192.168.40.0/24 — 192.168.40.1 |
| 50 | Printers | 192.168.50.0/24 — 192.168.50.1 |
| 99 | Management | 192.168.99.0/24 — 192.168.99.1 |
| 999 | Unused-port parking VLAN | No IP address |

The printer is statically addressed at `192.168.50.10`. The external payment server is `198.51.100.2`.

## Technologies documented
- VLAN segmentation and trunking
- Inter-VLAN routing on L3-SW1
- DHCP for selected client VLANs
- Guest ACL restricting access to internal private address space
- NAT/PAT on EDGE-R1
- Static routing and ISP connectivity
- SSH-based switch management
- Access-layer security, including unused-port shutdown and port-security configuration

## External payment-server traffic
The documented path is endpoint → access switch → L3-SW1 → EDGE-R1 → ISP-R1 → payment server. The documentation records PAT on EDGE-R1 as functioning in this simulation.

## Topology diagram status
The recovered technical document explicitly states that the original topology image was not included in that document. The diagram folder is therefore awaiting the original image; no replacement diagram has been fabricated.

## Project files
- `documentation/retail-store-network-documentation.docx` — recovered technical documentation.
- `diagrams/` — reserved for the original Packet Tracer topology image when available.

## Disclaimer
This is an independently developed simulated project in Cisco Packet Tracer, not a commercial production deployment. Test guidance is not presented as proof that every suggested test has passed.
