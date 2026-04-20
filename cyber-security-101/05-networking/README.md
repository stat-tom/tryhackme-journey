# Section 05 – Networking

Networking concepts, protocols, and practical tools for capturing and analysing traffic.

## Rooms

- [x] Networking Concepts
- [x] Networking Essentials
- [ ] Core Networking Protocols
- [ ] Secure Networking Protocols
- [ ] Wireshark: The Basics
- [ ] Tcpdump: The Basics
- [ ] Nmap: The Basics

## Notes

### Task 1 – Introduction

Networking concepts, protocols, and practical tools for capturing and analysing traffic.

### Task 2 – DHCP: Give Me My Network Settings

A device needs three basic settings to join a network:

- IP address + subnet mask
- gateway/router
- DNS server

DHCP automatically gives devices these values so users don’t have to type them manually and the network avoids duplicate IP addresses. It runs over UDP, with the server listening on port 67 and clients using port 68.

DHCP uses the DORA process:

- Discover: client searches for DHCP servers
- Offer: server replies with configuration details
- Request: client asks for a chosen offer
- Acknowledge: server confirms the lease

The message names are:

- DHCPDISCOVER: client broadcasts a request to find a DHCP server
- DHCPOFFER: server offers an available IP address
- DHCPREQUEST: client asks for the offered IP
- DHCPACK: server confirms the assignment

When the client sends DHCPDISCOVER it has no address yet, so it uses source `0.0.0.0` and broadcasts to destination `255.255.255.255` to reach any local DHCP server.

At the end of the exchange, the client has everything needed to use the network and connect to the Internet. The server typically provides:

- the leased IP address for this device
- the gateway to send traffic beyond the local network
- a DNS server to resolve hostnames into IP addresses

### Task 3 – ARP: Bridging Layer 3 Addressing to Layer 2 Addressing

On a local Ethernet or WiFi segment, knowing the IP address is not enough for delivery. The host must also find the MAC address for the destination, and that is what ARP (Address Resolution Protocol) does. ARP translates the target IP into a layer 2 address so the packet can be placed inside a frame.

An Ethernet frame header contains:

- destination MAC address
- source MAC address
- type field (for example, IPv4)

### Task 4 – ICMP: Troubleshooting Networks

ICMP (Internet Control Message Protocol) is a network-layer protocol used mostly for diagnostics and reporting problems rather than carrying user data. It helps devices tell each other when packets cannot be delivered, and it is the foundation for two common troubleshooting commands:

- `ping`: sends ICMP echo requests to a target host and waits for replies. It is useful to check whether the host is reachable and to measure the round-trip time of packets.
- `traceroute` (Linux) / `tracert` (MS Windows): discovers the path packets take from your system to a destination. Each hop along the route responds with an ICMP message, revealing the intermediate routers and where delays or failures occur.

IPv4 packets include a Time-to-Live (TTL) field that limits how many routers the packet can traverse. Each router decrements the TTL by one before forwarding the packet. When TTL reaches zero, the router drops the packet and sends back an ICMP Time Exceeded message (ICMP Type 11). In this context, “time” is counted in routers crossed, not seconds.

These tools are valuable for verifying connectivity, identifying network problems, and understanding the route traffic follows between hosts.

### Task 5 – Routing

*(Add routing details here.)*

### Task 6 – NAT

*(Add NAT details here.)*

