# **Linux Command Cheat Sheet**

## 📚 **Table of Contents**

- [🗂️ File and Directory Management](#file-and-directory-management)
- [🛡️ Permissions and Ownership](#permissions-and-ownership)
- [📄 Viewing and Manipulating File Content](#viewing-and-manipulating-file-content)
- [🔍 System Information and Monitoring](#system-information-and-monitoring)
- [🧠 Process Management](#process-management)
- [🔐 User Management](#user-management)
- [🌐 Networking](#networking)
- [🧰 System Utilities](#system-utilities)
- [📦 File Archiving and Compression](#file-archiving-and-compression)
- [📁 Special File System Paths](#special-file-system-paths)
- [🗃️ Key Directories in the Linux File System](#key-directories-in-the-linux-file-system)
- [🔧 Advanced File Operations](#advanced-file-operations)
- [🖥️ Terminal Navigation Shortcuts](#terminal-navigation-shortcuts)
- [🧹 Cleanup Commands](#cleanup-commands)
- [🧾 Logs and System Info](#logs-and-system-info)
- [📊 Disk Usage Utilities](#disk-usage-utilities)
- [🕵️ Security & Permissions Checks](#security--permissions-checks)
- [🌐 Package Management (Debian-based)](#package-management-debian-based)
- [🧪 Scripting Essentials (Bash)](#scripting-essentials-bash)
- [🧱 Filesystem and Partition Tools](#filesystem-and-partition-tools)
- [⚡ Startup & Services (Systemd)](#startup--services-systemd)
- [🧾 Package Log & System Log Monitoring](#package-log--system-log-monitoring)
- [⚠️ May Require Extra Installation](#may-require-extra-installation-on-some-distros)

> _Note_: ✅ All Commands will work perfectly fine on Debian-Based Specific (Ubuntu, Kali, Debian) Systems some of the later commands may not work on Non-Debian-Based Systems.

---

## File and Directory Management

- `cd`: Change the current directory.
- `cd ..`: Move up one directory level.
- `cd ~`: Go to the home directory.
- `pwd`: Print the current working directory.
- `ls`: List files and directories.
- `ls -l`: Long listing format.
- `ls -a`: List all files including hidden ones.
- `ls -la`: Long listing of all files including hidden ones (shows permissions, ownership, size, modified time).
- `mkdir <dir_name>`: Create a new directory.
- `rmdir <dir_name>`: Remove an empty directory.
  > ⚠️ Cannot remove if the directory is not empty.
- `rm <file_name>`: Remove a file.
- `mv <source> <destination>`: Move or rename a file/directory.
- `cp <source> <destination>`: Copy files or directories.
- `touch <file_name>`: Create an empty file or update timestamp.
- `find <path> -name <file_name>`: Search for files in a directory hierarchy.
- `locate <file_name>`: Quickly find files by name.

---

## Permissions and Ownership

- `chmod <permissions> <file/dir>`: Change file permissions.
  > 📝 4 = read, 2 = write, 1 = execute (applied as owner-group-others).
- `chown <user> <file/dir>`: Change file owner.
- `chgrp <group> <file/dir>`: Change group ownership.

---

## Viewing and Manipulating File Content

- `cat <file>`: Display file contents.
- `less <file>`: Scrollable view of file content (use `q` to quit).
- `more <file>`: Paginated file viewer.
- `head <file>`: Show first 10 lines.
  > Use `head -n <lines> <file>` for a custom number.
- `tail <file>`: Show last 10 lines.
  > Use `tail -n <lines> <file>` for a custom number.
- `grep <pattern> <file>`: Search for pattern in a file.
  > `grep -r <pattern> <dir>` to search recursively.
- `wc <file>`: Count lines, words, and characters.
  > Use `wc -l`, `wc -w`, or `wc -c` for specific counts.

---

## System Information and Monitoring

- `whoami`: Display current username.
- `id`: Show UID, GID, and groups of the current user.
- `uptime`: Show how long the system has been running.
- `hostname`: Display system hostname.
- `uname`: Show OS info.
  > Use `uname -a` for all system details.
- `df`: Show disk space usage.
  > Use `df -h` for human-readable format.
- `du <file/dir>`: Estimate file/directory space usage.
- `free`: Show memory usage.
- `date`: Show current date and time.
- `history`: Show previously run commands.

---

## Process Management

- `ps`: Display active processes.
  > Use `ps aux` for detailed info.
- `top`: Live view of processes and resource usage.
- `kill <pid>`: Kill process by ID.
- `killall <name>`: Kill processes by name.
- `xargs <command>`: Execute commands from input (e.g., `find ... | xargs rm`).

---

## User Management

- `sudo useradd -m <user>`: Create a new user with home directory.
- `cat /etc/passwd`: View all system users and details.

---

## Networking

- `ping <host>`: Check network connectivity.
- `traceroute <host>`: Show route to host.
- `netstat`: View network connections, routing tables, etc.
- `ifconfig`: Show or configure network interfaces.
- `ip <args>`: Advanced IP networking commands.
- `ssh <user>@<host>`: Connect to remote host via SSH.
- `scp <source> <dest>`: Secure copy files between systems.
- `rsync <src> <dest>`: Sync files between systems.
- `wget <url>`: Download files from web.
- `curl <url>`: Transfer data to/from a URL.

---

## System Utilities

- `man <command>`: View the manual for a command.
- `clear`: Clear the terminal screen.
- `alias <name>='<command>'`: Create a command alias.
- `unalias <name>`: Remove a command alias.
- `echo <text>`: Print a line of text.
- `export <var>=<value>`: Set an environment variable.
- `env`: Show all environment variables.
- `printenv <var>`: Show the value of an environment variable.
- `unset <var>`: Unset an environment variable.
- `which <command>`: Show the full path of a command.
- `whereis <command>`: Show location of command's binary, source, and man page.

---

## File Archiving and Compression

- `tar -cvf <archive.tar> <files>`: Create tar archive.
  > Use `tar -xvf <archive.tar>` to extract.
- `zip <archive.zip> <files>`: Create zip archive.
  > Use `unzip <archive.zip>` to extract.
- `gzip <file>`: Compress file with gzip.
  > Use `gunzip <file.gz>` to decompress.
- `bzip2 <file>`: Compress file with bzip2.
  > Use `bunzip2 <file.bz2>` to decompress.

---

## Special File System Paths

- `/`: Root directory.
- `.`: Current directory.
- `..`: Parent directory.
- `~`: Home directory.

---

## Key Directories in the Linux File System

### **1. `/bin` – Essential User Binaries**

- Common programs needed by all users (e.g. `ls`, `cp`, `mv`, `grep`, `ping`)

### **2. `/sbin` – System Binaries**

- System programs for superusers (e.g. `iptables`, `ifconfig`, `reboot`)

### **3. `/etc` – Configuration Files**

- Stores system-wide config files (e.g. `/etc/passwd`, `/etc/apache/`)

### **4. `/var` – Variable Files**

- Log files, spool files, etc. (e.g. `/var/log/`)

### **5. `/tmp` – Temporary Files**

- Temporary files deleted on reboot

### **6. `/home` – User Home Directories**

- Each user has a folder here (`/home/username`)

### **7. `/boot` – Boot Loader Files**

- Contains kernel, bootloader configs (`vmlinuz`, `grub/`)

---

## Advanced File Operations

- `stat <file>`: Detailed file info (inode, access/change time, etc.)
- `file <file>`: Identify file type (text, binary, image, etc.)
- `basename <path>`: Strip directory to get filename only
- `dirname <path>`: Extract directory path
- `readlink -f <file>`: Resolve full path of symbolic link

---

## Terminal Navigation Shortcuts

| Shortcut     | Description                                       |
| ------------ | ------------------------------------------------- |
| `Ctrl + A`   | Go to beginning of line                           |
| `Ctrl + E`   | Go to end of line                                 |
| `Ctrl + U`   | Cut text from cursor to beginning                 |
| `Ctrl + K`   | Cut text from cursor to end                       |
| `Ctrl + R`   | Reverse search through command history            |
| `!!`         | Repeat last command                               |
| `!<command>` | Run last occurrence of that command (e.g., `!ls`) |

---

## Cleanup Commands

- `rm -rf <dir>`: Force delete directory and contents (**use with caution**)
- `truncate -s 0 <file>`: Empty file without deleting
- `> <file>`: Another way to empty a file

---

## Logs and System Info

- `dmesg`: Show kernel ring buffer messages (hardware events)
- `journalctl`: Show logs from `systemd` (e.g. `journalctl -xe`)
- `last`: Show recent logins
- `who`: Show who is currently logged in
- `uptime -p`: Uptime in human-readable format

---

## Disk Usage Utilities

- `ncdu`: Interactive disk usage viewer (install separately)
- `lsblk`: Show block device info (disks, partitions)
- `mount` / `umount`: Mount/unmount filesystems
- `df -Th`: Disk space with type info
- `du -sh *`: Show size of all files/folders in current dir (human-readable)

---

## Security & Permissions Checks

- `umask`: Show or set default permissions for new files
- `lsattr`: Show extended file attributes
- `getfacl <file>` / `setfacl`: Manage Access Control Lists (ACLs)
- `sudo visudo`: Safely edit sudoers file
- `passwd <user>`: Set/change a user's password

---

## Package Management (Debian-based)

- `apt update`: Refresh package lists
- `apt upgrade`: Upgrade all installed packages
- `apt install <pkg>`: Install package
- `apt remove <pkg>`: Remove package
- `dpkg -l`: List installed packages
- `dpkg -i <.deb>`: Install `.deb` file manually

---

## Scripting Essentials (Bash)

- `#!/bin/bash`: Shebang to specify interpreter
- `$(command)` or `` `command` ``: Command substitution
- `if`, `else`, `fi`, `for`, `while`: Basic control flow
- `echo $VAR`: Access variables
- `read VAR`: Get user input

---

## Filesystem and Partition Tools

- `fdisk -l`: List disks and partitions
- `mkfs.ext4 /dev/sdX`: Format a partition as ext4
- `tune2fs`: Adjust filesystem parameters
- `e2fsck`: Check/repair ext2/ext3/ext4 filesystems

---

## Startup & Services (Systemd)

- `systemctl status <service>`: Show service status
- `systemctl start|stop|restart <service>`
- `systemctl enable|disable <service>`: Auto-start at boot
- `systemctl list-units --type=service`: List all services
- `systemctl is-active <service>`: Check if service is running

---

## Package Log & System Log Monitoring

- `cat /var/log/dpkg.log | tail -n 10`  
  ➤ Show the last 10 package operations (installs, removals, upgrades)

- `tail -f /var/log/syslog`  
  ➤ Continuously follow system logs in real-time (great for debugging)

- `grep "install " /var/log/dpkg.log`  
  ➤ List all packages that were installed (recently or historically)

- `zcat /var/log/dpkg.log.1.gz | grep upgrade`  
  ➤ Search archived logs for past package upgrades

- `less /var/log/apt/history.log`  
  ➤ View apt install history in a scrollable format

- `journalctl -u <service>`  
  ➤ Show logs for a specific systemd service (e.g., `ssh`, `docker`)

- `journalctl -f`  
  ➤ Real-time system log viewer (like `tail -f` but for journalctl)

- `tail -n 100 /var/log/auth.log`  
  ➤ View the last 100 authentication-related log entries

---

## May Require Extra Installation (on Some Distros)

| Command      | Notes                                                                |
| ------------ | -------------------------------------------------------------------- |
| `ifconfig`   | Often deprecated in favor of `ip`. Available in `net-tools` package. |
| `netstat`    | Also part of `net-tools`. Use `ss` as modern alternative.            |
| `traceroute` | May need to be installed (`sudo apt install traceroute`)             |

---
