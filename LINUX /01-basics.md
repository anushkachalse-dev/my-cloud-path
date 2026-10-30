# Linux Notes - Day 1: Basics

# What is Linux?
- Free, open-source operating system
- Most cloud servers (AWS EC2, Azure VMs) run Linux
- Servers have no desktop, only a terminal
- Commands are the main way to work

# Setup (WSL)
- Open PowerShell as administrator
- Run `wsl --install`
- Restart the computer
- Open Ubuntu from the Start menu
- Create a username and password

# Reading the prompt
- `user@computer:~$`
- `user` = my username
- `computer` = computer name
- `~` = home folder
- `$` = normal user
- `#` = root (admin)

# Filesystem
- No C: or D: drives
- Everything is one tree starting at `/` (root)
- `/home` = personal files
- `/etc` = configuration files
- `/var/log` = system logs
- `/usr` = installed programs
- `/bin` = essential commands
- `/tmp` = temporary files

# Paths
- Absolute path starts from `/` (example: `/var/log`)
- Relative path starts from where I am (example: `docs/a.txt`)
- `.` = current folder
- `..` = parent folder
- `~` = home folder

# Commands learned
- `pwd` = show current folder
- `ls` = list files
- `ls -a` = show hidden files
- `ls -l` = detailed list
- `cd folder` = go into a folder
- `cd ..` = go up one level
- `cd ~` = go to home
- `mkdir name` = create a folder
- `touch file.txt` = create an empty file
- `clear` = clear the screen

# Key takeaway
- Folders are like rooms in a house
- I am always standing in one room
- `pwd` tells me which room
