# Linux Notes - Day 1: Basics

# What is Linux?
- A free, open-source operating system.
- Most cloud servers (AWS EC2, Azure VMs) run Linux.
- Servers usually have no desktop, only a terminal, so commands are the main way to work.

# Setup (Ubuntu on Windows with WSL)
1. Open PowerShell as administrator.
2. Run `wsl --install`
3. Restart the computer.
4. Open Ubuntu from the Start menu and create a username and password.

# Reading the prompt
`user@computer:~$`
- `user` = my username
- `computer` = computer name
- `~` = home folder
- `$` = normal user (`#` = root/admin)

# Filesystem
Linux has no C: or D: drives. Everything is one tree starting at `/` (root).

| Folder | What it holds |
|--------|---------------|
| `/home` | personal files |
| `/etc` | configuration files |
| `/var/log` | system logs |
| `/usr` | installed programs |
| `/bin` | essential commands |
| `/tmp` | temporary files |

# Paths
- **Absolute:** starts from `/`, e.g. `/var/log`
- **Relative:** starts from where I am, e.g. `docs/a.txt`
- `.` = current folder, `..` = parent folder, `~` = home folder

# Commands learned
| Command | Meaning |
|---------|---------|
| `pwd` | show current folder |
| `ls` | list files |
| `ls -a` | include hidden files |
| `ls -l` | detailed list |
| `cd folder` | go into a folder |
| `cd ..` | go up one level |
| `cd ~` | go to home |
| `mkdir name` | create a folder |
| `touch file.txt` | create an empty file |
| `clear` | clear the screen |

# Key takeaway
Think of folders as rooms in a house. I am always standing in one room, and `pwd` tells me which.
