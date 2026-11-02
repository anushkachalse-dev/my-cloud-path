 #Root Access & Directory Navigation

 1. Introduction
Linux is a multi-user operating system. Every user has a defined level of access, which controls what they can read, change, or run. This keeps the system secure and organized.

 2. Root User
The root user is the superuser of a Linux system. It has unrestricted access to all files, commands, and system settings.

- Can install, modify, and delete any software or file
- Can manage other users and permissions
- Misuse can damage the system, so root access should be used carefully

 3. Switching to Root: `sudo -i`
`sudo` (Superuser Do) lets a permitted user run commands with administrator privileges. The `-i` option starts an interactive login shell as root. This is safer than logging in as root directly, because access is granted only when needed and is tied to a user's sudo rights.

 4. Checking the Current User: `whoami`
This command prints the username of the account currently in use. After running `sudo -i`, it returns `root`, which confirms the switch.

 5. Root Directory: `/`
The root directory (`/`) is the top level of the Linux file system. All other files and directories branch from it, forming a single tree structure. Do not confuse it with the root user's home directory, which is `/root`.

 6. Navigating: `cd`
`cd` (Change Directory) moves the user from one directory to another.

- `cd /` goes to the root directory
- `cd ..` goes up one level
- `cd ~` goes to the user's home directory

 7. Listing Contents: `ls`
`ls` displays the files and directories in the current location. It is used to see what a directory contains before working with it.

 8. Linux Directory Structure
 Directory  Purpose 
--------------------
 `/bin` - Essential user commands 
 `/etc` - System configuration files 
 `/home` - Home directories of regular users 
 `/root`- Home directory of the root user 
 `/var` - Logs and variable data 
 `/tmp` - Temporary files 
 `/usr` - User programs and libraries 

 9. Conclusion
Understanding users, root privileges, and the directory hierarchy is the foundation of Linux administration. These concepts are essential for working with servers and cloud environments.
