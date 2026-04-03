# Section 03 – Windows and AD Fundamentals

Windows operating system basics and an introduction to Active Directory.

## Rooms

- [x] Windows Fundamentals 1
- [ ] Windows Fundamentals 2
- [ ] Windows Fundamentals 3
- [ ] Active Directory Basics

## Notes

### Windows Fundamentals 1

Introduced the core parts of the Windows operating system from a user and administrator perspective. The room covered common Windows editions, the desktop interface, the structure of the Windows filesystem, important system folders such as `System32`, user accounts and permissions, User Account Control, the Settings and Control Panel interfaces, and Task Manager.

Key topics:

- Differences between Windows editions and the features aimed at home, professional, and enterprise use.
- The Windows desktop environment, including the Start menu, taskbar, and File Explorer.
- The Windows filesystem layout, especially directories under `C:\Windows` and user profile folders.
- The purpose of `C:\Windows\System32` as a central directory for core system files and utilities.
- User accounts, profile folders, permissions, and the role of administrators versus standard users.
- User Account Control as a safeguard for privileged actions.
- The difference between Settings and Control Panel for managing system configuration.
- Task Manager for reviewing running apps, background processes, and system resource usage.

Sample commands:

```powershell
systeminfo
whoami /priv
hostname
tasklist
ipconfig /all
dir C:\Windows\System32
echo %USERNAME%
control
ms-settings:
```

What these commands do:

- `systeminfo` displays Windows version details, installed updates, and hardware summary information.
- `whoami /priv` shows the current account and the privileges assigned to it.
- `hostname` prints the computer name.
- `tasklist` lists running processes.
- `ipconfig /all` shows detailed network adapter configuration.
- `dir C:\Windows\System32` lists files in the `System32` directory.
- `echo %USERNAME%` prints the current Windows username in Command Prompt.
- `control` opens Control Panel.
- `ms-settings:` opens the Windows Settings app when run from a supported shell or Run dialog.
