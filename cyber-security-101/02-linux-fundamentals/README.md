# Section 02 – Linux Fundamentals

Core Linux skills: command-line navigation, file permissions, and shell scripting basics.

## Rooms

- [ ] Linux Fundamentals Part 1
- [ ] Linux Fundamentals Part 2
- [ ] Linux Fundamentals Part 3

## Notes

### Linux Fundamentals Part 1

Covered the basics of working with a Linux machine from the terminal. The room introduced the Linux environment, showed how to connect to and interact with a machine in the browser, and walked through the first commands needed to move around the system and inspect files.

Key topics:

- Linux as a command-line-driven operating system commonly used in security, servers, and automation.
- Basic terminal interaction with commands to identify the current user, current directory, and directory contents.
- Filesystem navigation using commands to move between directories and inspect files.
- Searching for files and text with built-in command-line tools.
- Shell operators for chaining commands and redirecting output.

Sample commands:

```bash
pwd
whoami
ls
ls -la
cd /home
cat file.txt
find / -name "*.txt" 2>/dev/null
grep "password" notes.txt
echo "hello" > hello.txt
cat hello.txt | grep hello
```

What these commands do:

- `pwd` shows the current working directory.
- `whoami` prints the current logged-in user.
- `ls` and `ls -la` list directory contents, including hidden files with detailed output.
- `cd /home` changes into the `/home` directory.
- `cat file.txt` prints a file's contents.
- `find / -name "*.txt" 2>/dev/null` searches for text files while hiding permission errors.
- `grep "password" notes.txt` searches for matching text inside a file.
- `echo "hello" > hello.txt` writes text into a file using output redirection.
- `cat hello.txt | grep hello` passes command output through a pipe to filter results.

### Linux Fundamentals Part 2

Built on the first room by moving from simple navigation to practical system usage. The room covered connecting to a Linux machine over SSH, using command flags to change command behavior, working further with the filesystem, understanding Linux permissions, and learning the purpose of common system directories.

Key topics:

- Connecting to remote Linux machines using SSH.
- Using flags and switches such as `-l`, `-a`, and `-h` to modify command output.
- Creating, moving, copying, and deleting files and directories.
- Reading and interpreting Linux file permissions for users, groups, and others.
- Recognizing common directories such as `/etc`, `/home`, `/var`, and `/tmp`.

Sample commands:

```bash
ssh user@10.10.10.10
cp notes.txt backup-notes.txt
mv backup-notes.txt /tmp/backup-notes.txt
mkdir projects
touch projects/todo.txt
chmod 644 projects/todo.txt
rm backup-notes.txt
file /bin/bash
stat projects/todo.txt
```

What these commands do:

- `ssh user@10.10.10.10` connects to a remote Linux machine over SSH.
- `cp notes.txt backup-notes.txt` copies a file.
- `mv backup-notes.txt /tmp/backup-notes.txt` moves or renames a file.
- `mkdir projects` creates a new directory.
- `touch projects/todo.txt` creates an empty file.
- `chmod 644 projects/todo.txt` sets standard read/write permissions for the owner and read-only for others.
- `rm backup-notes.txt` deletes a file that is no longer needed.
- `file /bin/bash` identifies the type of a file or binary.
- `stat projects/todo.txt` shows detailed metadata, including permissions and timestamps.

### Linux Fundamentals Part 3

Expanded from file and permission basics into day-to-day Linux administration. The room covered connecting to a deployed machine, editing files in the terminal, using common utility commands, understanding and managing processes, automating recurring tasks, working with package managers, and reviewing system logs.

Key topics:

- Editing text directly in the terminal with command-line editors.
- Using general-purpose utilities to download files, inspect network connectivity, and gather system information.
- Viewing and controlling running processes.
- Scheduling automated tasks for routine maintenance.
- Installing and updating software through the system package manager.
- Checking log files and system journals for troubleshooting.

Sample commands:

```bash
nano notes.txt
wget http://example.com/file.txt
ps aux
kill 1234
crontab -e
apt update
apt install htop
journalctl -xe
tail -f /var/log/syslog
```

What these commands do:

- `nano notes.txt` opens a terminal text editor for creating or modifying a file.
- `wget http://example.com/file.txt` downloads a file from a URL.
- `ps aux` lists running processes for all users with detailed information.
- `kill 1234` stops the process with PID `1234`.
- `crontab -e` opens the current user's cron schedule for editing automated tasks.
- `apt update` refreshes the package index from configured repositories.
- `apt install htop` installs a package using the APT package manager.
- `journalctl -xe` shows recent system journal entries with extra detail.
- `tail -f /var/log/syslog` follows a log file in real time as new entries are written.
