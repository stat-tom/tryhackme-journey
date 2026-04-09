# Section 04 – Command Line

Working with the Windows Command Prompt, PowerShell, and Linux shells.

## Rooms

- [x] Windows Command Line
- [ ] Windows PowerShell
- [ ] Linux Shells

## Notes

### Windows Command Line

#### `ipconfig`
Displays basic IP configuration details for each network adapter, such as IPv4 address, subnet mask, and default gateway.

Example:

```cmd
ipconfig
```

Use this when you want a quick view of your current network settings.

#### `ipconfig /all`
Shows full TCP/IP configuration details, including MAC address, DHCP status, DNS servers, and lease information.

Example:

```cmd
ipconfig /all
```

Use this for more detailed troubleshooting than the standard `ipconfig` output.

#### `ver`
Displays the Windows version currently running in Command Prompt.

Example:

```cmd
ver
```

This is useful for quickly confirming the OS version from the CLI.

#### `set`
Displays, creates, or modifies environment variables for the current Command Prompt session.

Examples:

```cmd
set
set username=student
set username
```

This helps when checking variables like `PATH` or setting temporary values for scripts.

#### `systeminfo`
Displays detailed system information, including OS version, hostname, installed hotfixes, boot time, RAM, and domain details.

Example:

```cmd
systeminfo
```

Useful for host enumeration and general system profiling.

#### `ping`
Tests connectivity to another host by sending ICMP Echo Request packets and measuring the response time.

Examples:

```cmd
ping 8.8.8.8
ping google.com
```

Use this to check whether a host is reachable and whether DNS resolution works.

#### `tracert`
Shows the route packets take to a destination and the hops between your machine and the target.

Example:

```cmd
tracert google.com
```

Useful for identifying where connectivity issues happen across a network path.

#### `nslookup`
Queries DNS to resolve domain names to IP addresses or retrieve DNS records from a DNS server.

Examples:

```cmd
nslookup google.com
nslookup tryhackme.com 8.8.8.8
```

This is commonly used to verify DNS resolution and test specific DNS servers.

#### `netstat`
Displays active network connections, listening ports, and protocol statistics.

Example:

```cmd
netstat
```

Useful for checking which connections are currently established on the system.

#### `netstat -abon`
Displays all active connections and listening ports, shows the executable name, uses numerical addresses, and includes the process ID. Running this often requires an elevated Command Prompt.

Example:

```cmd
netstat -abon
```

Flags used:

- `-a`: Show all active connections and listening ports.
- `-b`: Show the executable involved in creating each connection.
- `-o`: Show the owning process ID (PID).
- `-n`: Show addresses and port numbers numerically.

This is especially useful during incident response or local host enumeration to map open ports back to running processes.
