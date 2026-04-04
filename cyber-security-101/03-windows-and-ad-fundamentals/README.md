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

### Windows Fundamentals 2

Based on the room tasks, this room focused on core Windows administration utilities including System Configuration and Advanced System Settings, UAC settings, Computer Management, System Information, Resource Monitor, Command Prompt, and Registry Editor.

Key topics:

- System Configuration (`msconfig`) for boot options, services, startup-related settings, and troubleshooting.
- Advanced System Settings for environment variables, performance options, startup and recovery settings, and remote access configuration.
- User Account Control tuning and how elevation prompts affect administrative actions.
- Computer Management as a central console for Event Viewer, Shared Folders, Device Manager, Local Users and Groups, and Disk Management.
- System Information (`msinfo32`) for reviewing hardware resources, components, and software environment details.
- Resource Monitor (`resmon`) for drilling into CPU, memory, disk, and network activity.
- Command Prompt for running system utilities and quick administrative checks.
- Registry Editor (`regedit`) for viewing and modifying Windows configuration stored in the registry.

Ways to see startup programs:

- On Windows clients, open Task Manager and review the `Startup` or `Startup apps` section to see enabled startup entries and their impact.
- On Windows clients, open Settings and navigate to `Apps > Startup` on supported versions to view and toggle startup applications.
- On Windows clients and Windows Server, run `msconfig` and review startup-related options; on newer versions this often redirects startup app management to Task Manager.
- On Windows Server, check the Startup folders for per-user and all-user logon items: `C:\Users\<username>\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup` and `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp`.
- On Windows clients and Windows Server, inspect the `Run` and `RunOnce` registry keys in `HKCU` and `HKLM` with Registry Editor to find programs launched at logon.
- On Windows Server, review scheduled tasks in Task Scheduler because many startup or logon-triggered programs are configured there instead of the Startup folder.

Sample commands:

```powershell
msconfig
sysdm.cpl
compmgmt.msc
msinfo32
resmon
regedit
cmd
schtasks /query /fo LIST /v
reg query "HKLM\Software\Microsoft\Windows\CurrentVersion\Run"
reg query "HKCU\Software\Microsoft\Windows\CurrentVersion\Run"
```

What these commands do:

- `msconfig` opens System Configuration.
- `sysdm.cpl` opens System Properties, including Advanced System Settings.
- `compmgmt.msc` opens the Computer Management console.
- `msinfo32` opens System Information.
- `resmon` opens Resource Monitor.
- `regedit` opens Registry Editor.
- `cmd` opens Command Prompt.
- `schtasks /query /fo LIST /v` lists scheduled tasks in verbose form, which helps identify logon and startup-related tasks.
- `reg query "HKLM\Software\Microsoft\Windows\CurrentVersion\Run"` displays machine-wide startup entries from the registry.
- `reg query "HKCU\Software\Microsoft\Windows\CurrentVersion\Run"` displays per-user startup entries from the registry.
