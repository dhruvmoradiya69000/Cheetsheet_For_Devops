# Linux Command Cheat Sheet

## Table of Contents
 - [File and Directory Operations](#file-and-directory-operations)
 - [File Viewing and Editing](#file-viewing-and-editing)
 - [File Permissions](#file-permissions)
 - [System Information](#system-information)
 - [Package Management (Ubuntu/Debian)](#package-management-ubuntudebian)
 - [Networking](#networking)
 - [Process Management](#process-management)
 - [Text Processing](#text-processing)
 - [Advanced File Operations](#advanced-file-operations)
 - [Text Processing and Analysis](#text-processing-and-analysis)
 - [System Monitoring and Performance](#system-monitoring-and-performance)
 - [User and Group Management](#user-and-group-management)
 - [Shell Scripting](#shell-scripting)
 - [Networking Tools](#networking-tools)

## File and Directory Operations

| Command | Description |
|---------|-------------|
| `ls` | List directory contents |
| `cd <directory>` | Change directory |
| `pwd` | Print working directory |
| `mkdir <directory>` | Create a new directory |
| `rm <file>` | Remove a file |
| `rm -r <directory>` | Remove a directory and its contents |
| `cp <source> <destination>` | Copy files or directories |
| `mv <source> <destination>` | Move or rename files or directories |
| `touch <file>` | Create an empty file or update timestamp |

## File Viewing and Editing

| Command | Description |
|---------|-------------|
| `cat <file>` | Display file contents |
| `less <file>` | View file contents with pagination |
| `head <file>` | Display the first few lines of a file |
| `tail <file>` | Display the last few lines of a file |
| `nano <file>` | Open a text editor for file editing |
| `vim <file>` | Open the Vim text editor |

## File Permissions

| Command | Description |
|---------|-------------|
| `chmod <permissions> <file>` | Change file permissions |
| `chown <user>:<group> <file>` | Change file ownership |

## System Information

| Command | Description |
|---------|-------------|
| `uname -a` | Display system information |
| `top` | Show running processes and system resources |
| `df -h` | Show disk space usage |
| `free -h` | Display memory usage |

## Package Management (Ubuntu/Debian)

| Command | Description |
|---------|-------------|
| `apt update` | Update package lists |
| `apt upgrade` | Upgrade installed packages |
| `apt install <package>` | Install a package |
| `apt remove <package>` | Remove a package |

## Networking

| Command | Description |
|---------|-------------|
| `ifconfig` | Display network interface configuration |
| `ping <host>` | Send ICMP echo request to a host |
| `ssh <user>@<host>` | Connect to a remote host via SSH |
| `scp <source> <destination>` | Securely copy files between hosts |

## Process Management

| Command | Description |
|---------|-------------|
| `ps aux` | List all running processes |
| `kill <PID>` | Terminate a process by its ID |
| `killall <name>` | Terminate processes by name |

## Text Processing

| Command | Description |
|---------|-------------|
| `grep <pattern> <file>` | Search for a pattern in a file |
| `sed 's/old/new/g' <file>` | Stream editor for text manipulation |
| `awk '{print $1}' <file>` | Pattern scanning and text processing |

## Advanced File Operations

| Command | Description |
|---------|-------------|
| `find <path> -name "<pattern>"` | Search for files matching a pattern |
| `tar -cvf <archive.tar> <files>` | Create a tar archive |
| `tar -xvf <archive.tar>` | Extract a tar archive |
| `gzip <file>` | Compress a file using gzip |
| `gunzip <file.gz>` | Decompress a gzip file |

## Text Processing and Analysis

| Command | Description |
|---------|-------------|
| `wc <file>` | Count lines, words, and characters in a file |
| `sort <file>` | Sort lines of text |
| `uniq <file>` | Report or omit repeated lines |
| `cut -d: -f1 <file>` | Cut out selected portions of each line |
| `tr 'a-z' 'A-Z' < <file>` | Translate characters |

## System Monitoring and Performance

| Command | Description |
|---------|-------------|
| `htop` | Interactive process viewer |
| `iotop` | IO usage monitoring |
| `netstat -tuln` | List all listening ports |
| `lsof` | List open files |
| `vmstat` | Report virtual memory statistics |

## User and Group Management

| Command | Description |
|---------|-------------|
| `useradd <username>` | Create a new user |
| `userdel <username>` | Delete a user |
| `passwd <username>` | Change user password |
| `groupadd <groupname>` | Create a new group |
| `usermod -aG <group> <user>` | Add user to a group |

## Shell Scripting

| Command | Description |
|---------|-------------|
| `#!/bin/bash` | Shebang for Bash scripts |
| `$1, $2, ...` | Positional parameters |
| `$?` | Exit status of last command |
| `$#` | Number of command-line arguments |
| `if [ condition ]; then ... fi` | Conditional statement |
| `for i in {1..5}; do ... done` | For loop |

## Networking Tools

| Command | Description |
|---------|-------------|
| `dig <domain>` | DNS lookup utility |
| `nslookup <domain>` | Query DNS servers |
| `traceroute <host>` | Print the route packets take to a network host |
| `tcpdump` | Dump traffic on a network |
| `iptables -L` | List all firewall rules |

Remember to use `man <command>` for detailed information on any command!
