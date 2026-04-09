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

#### `cd`
Changes the current directory in Command Prompt.

Examples:

```cmd
cd C:\Users\student
cd Documents
```

Use this to navigate into a specific folder before running other commands.

#### `cd ..`
Moves up one level from the current directory to its parent directory.

Example:

```cmd
cd ..
```

This is useful for quickly stepping back through the folder structure.

#### `dir`
Lists the files and folders in the current directory.

Example:

```cmd
dir
```

Use this to see the contents of the current working directory.

#### `dir /a`
Lists all files and folders, including hidden and system items.

Example:

```cmd
dir /a
```

Useful when you want to reveal items not shown in a normal directory listing.

#### `dir /s`
Lists files and folders in the current directory and all subdirectories recursively.

Example:

```cmd
dir /s
```

Use this when you need a full recursive view of a directory tree.

#### `tree`
Displays the folder structure of a path in a tree-style layout.

Examples:

```cmd
tree
tree C:\Users\student\Documents
```

This is useful for visualizing nested directories.

#### `mkdir`
Creates a new directory.

Examples:

```cmd
mkdir notes
mkdir C:\Temp\Logs
```

Use this to create folders for organizing files or lab work.

#### `rmdir`
Removes a directory. The directory usually needs to be empty unless additional flags are used.

Examples:

```cmd
rmdir oldnotes
rmdir /s /q C:\Temp\OldLogs
```

Flags used in the second example:

- `/s`: Remove the directory and all contents.
- `/q`: Quiet mode without confirmation prompts.

Use this carefully, especially with `/s`, because it can remove entire directory trees.

#### `type`
Displays the contents of a text file in the terminal.

Example:

```cmd
type README.md
```

Useful for quickly reading small text files from Command Prompt.

#### `move`
Moves a file or folder from one location to another. It can also be used to rename files.

Examples:

```cmd
move notes.txt C:\Temp\
move draft.txt final.txt
```

Use this to reorganize files or rename them without opening File Explorer.

#### `del`
Deletes one or more files.

Examples:

```cmd
del notes.txt
del *.tmp
```

Use this carefully because deleted files are not moved to the Recycle Bin when removed from Command Prompt.

#### `copy *.md C:\Markdown`
Copies all Markdown files in the current directory to `C:\Markdown` using a wildcard pattern.

Example:

```cmd
copy *.md C:\Markdown
```

This command is useful when you want to bulk-copy files with the same extension into a central folder.

#### `tasklist`
Displays a list of currently running processes on the system.

Example:

```cmd
tasklist
```

Use this to see active processes, their process IDs, and memory usage.

#### `tasklist /FI "imagename eq sshd.exe"`
Displays only the processes that match the filter, in this case processes named `sshd.exe`.

Example:

```cmd
tasklist /FI "imagename eq sshd.exe"
```

Flags used:

- `/FI`: Apply a filter to the process list output.

This is useful when you want to quickly check whether a specific process is running.

#### `taskkill /PID 4567`
Terminates the process with the specified process ID.

Example:

```cmd
taskkill /PID 4567
```

Common related flag:

- `/F`: Force termination of the process if it does not close normally.

Use this carefully to stop a specific process after identifying its PID with `tasklist`.

#### `chkdsk`
Checks the file system and disk volumes for errors and can identify bad sectors.

Examples:

```cmd
chkdsk
chkdsk C:
```

This is useful for detecting file system problems or disk issues during troubleshooting.

#### `driverquery`
Displays a list of installed device drivers on the system.

Examples:

```cmd
driverquery
driverquery /v
```

Use this to review loaded drivers and gather host information during system enumeration.

#### `sfc /scannow`
Scans protected system files for corruption and repairs them automatically when possible.

Example:

```cmd
sfc /scannow
```

This is commonly used when Windows system files are suspected to be damaged or altered.

#### `shutdown /s`
Shuts down the computer.

Example:

```cmd
shutdown /s
```

Common related flag:

- `/t 0`: Shut down immediately without a delay.

Use this to power off the system from the command line.

#### `shutdown /a`
Aborts a pending system shutdown.

Example:

```cmd
shutdown /a
```

This only works if a shutdown has already been scheduled and is still waiting to occur.
