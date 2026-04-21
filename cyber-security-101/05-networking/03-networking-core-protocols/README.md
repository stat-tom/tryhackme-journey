# Networking Core Protocols

Learn about the core TCP/IP protocols.

## Key Topics

- TCP and UDP protocols
- IP protocol fundamentals
- WHOIS (domain information lookup)
- HTTP/HTTPS (web access)
- FTP (file transfer)
- SMTP (email sending)
- POP3 (email receiving)
- IMAP (email synchronization)
- Protocol operations and behavior

## Notes

### WHOIS: Domain Information Lookup

WHOIS is a query and response protocol used to retrieve information about domain registrations. It provides details about domain owners, registrars, and administrative contacts.

Example in CMD:
```cmd
whois example.com
```

### HTTP(S): Accessing the Web

HTTP (HyperText Transfer Protocol) is the foundation of web communication. HTTPS adds encryption via SSL/TLS to secure data transmission over the internet.

Example in CMD:
```cmd
curl -I https://example.com
```

### FTP: Transferring Files

FTP (File Transfer Protocol) is used for transferring files between computers over a network. It uses separate control and data connections and supports both active and passive modes.

Example in CMD:
```cmd
ftp ftp.example.com
```

### SMTP: Sending Email

SMTP (Simple Mail Transfer Protocol) handles the sending and routing of email messages. It operates on port 25 by default and works with mail servers to relay messages to their destinations.

Example in CMD:
```cmd
telnet smtp.example.com 25
```

### POP3: Receiving Email

POP3 (Post Office Protocol 3) allows clients to retrieve email messages from a mail server. It downloads messages to the local client and typically deletes them from the server.

Example in CMD:
```cmd
telnet pop.example.com 110
```

### IMAP: Synchronizing Email

IMAP (Internet Message Access Protocol) enables clients to access and synchronize email messages stored on a remote server. It supports organizing messages in folders and keeps emails synchronized across multiple devices.

Example in CMD:
```cmd
telnet imap.example.com 143
```
