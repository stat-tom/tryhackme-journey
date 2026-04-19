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

