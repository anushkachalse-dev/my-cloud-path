# User Management & File Permissions

 1. Introduction
Linux is a multi-user system, so every person or service that uses it needs an account. User management is the process of creating, organizing, and controlling these accounts. It keeps the system secure by making sure each user can access only what they are allowed to.

 2. Creating a User: `adduser`
The `adduser` command creates a new user account. It is an interactive command that:

- Creates the user's home directory (`/home/username`)
- Creates a primary group with the same name as the user
- Prompts for a password and optional details (full name, phone, etc.)

Root or sudo privileges are required to run it.

 3. Password Setup
During `adduser`, the system asks for a password and then asks to retype it. This confirmation prevents typing mistakes. Passwords are not stored in plain text. They are stored as hashes in `/etc/shadow`.

 4. User and Group IDs: `id`
Linux identifies users and groups by numbers, not names. The `id` command shows:

- **UID:** the user ID
- **GID:** the primary group ID
- **Groups:** all groups the user belongs to

Regular users usually get UIDs starting from 1000. The root user always has UID 0.

 5. Checking Group Membership: `groups`
The `groups` command lists all groups a user belongs to. Groups let administrators give the same permissions to many users at once, instead of setting them one by one.

 6. File Permissions: `ls -ltr`
`ls -ltr` shows a detailed (long) listing, sorted by modification time with the oldest first.

Example output:

    drwxr-xr-x 2 user group 4096 Nov 03 10:00 mydir

| Part | Meaning |
|------|---------|
| `d` | File type (`d` = directory, `-` = file) |
| `rwx` | Owner permissions |
| `r-x` | Group permissions |
| `r-x` | Others' permissions |
| `user` | Owner of the file |
| `group` | Group that owns the file |

 7. Permission Types
| Symbol | Permission | Meaning |
|--------|-----------|---------|
| `r` | Read | View file contents or list a directory |
| `w` | Write | Modify a file or add/remove files in a directory |
| `x` | Execute | Run a file or enter a directory |

 8. Ownership
Every file and directory has an owner and a group. Permissions are checked in this order: owner, then group, then others. This ownership model is how Linux protects files from unauthorized access.

 9. Conclusion
Users, groups, and permissions are the basis of Linux security. Understanding them is essential for managing servers, controlling access, and working in cloud environments.



#user management/commands.sh

sudo adduser <username>    # create a new user
id <username>              # show UID, GID, groups
groups <username>          # list user's groups
ls -ltr                    # long listing with permissions
