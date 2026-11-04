# Linux File Permissions: Theory Notes

 1. Introduction

Linux is a **multi-user operating system**, so it needs a way to control who can access which files. **File permissions** define what actions a user may perform on a file or directory. They protect data from unauthorized access and accidental changes, and they are a core part of Linux security.

 2. Types of Permissions

There are three basic permissions:

1. **Read (r)** - Allows viewing the contents of a file, or listing the contents of a directory.
2. **Write (w)** - Allows modifying a file, or creating, deleting, and renaming files inside a directory.
3. **Execute (x)** - Allows running a file as a program or script, or entering (using `cd`) a directory.

 3. User Categories

Permissions are assigned separately to three categories of users:

1. **Owner (u)** - The user who created the file.
2. **Group (g)** - A set of users who share access to the file.
3. **Others (o)** - Every other user on the system.

 4. Reading Permissions with `ls -l`

The command `ls -l` displays permissions as a 10-character string. Example:

```
-rw-r--r--
```

- **Character 1** is the file type: `-` for a regular file, `d` for a directory, `l` for a symbolic link.
- **Characters 2-4** are the owner's permissions.
- **Characters 5-7** are the group's permissions.
- **Characters 8-10** are the permissions for others.

In the example above, the owner can read and write, while the group and others can only read.

 5. Numeric (Octal) Representation

Each permission has a numeric value:

| Permission | Value |
|-----------|-------|
| Read (r) | 4 |
| Write (w) | 2 |
| Execute (x) | 1 |
| None (-) | 0 |

The values are added together for each category, giving one digit for the owner, one for the group, and one for others.

- `7` = 4+2+1 = `rwx`
- `6` = 4+2 = `rw-`
- `5` = 4+1 = `r-x`
- `4` = `r--`
- `0` = `---`

Common examples:

- **644** = `rw-r--r--` (typical for regular files)
- **755** = `rwxr-xr-x` (typical for scripts and directories)
- **600** = `rw-------` (private file, only the owner can read and write)

 6. Changing Permissions: `chmod`

The `chmod` (change mode) command modifies permissions. It works in two ways.

**Numeric mode** sets all permissions at once:

```bash
chmod 600 notes/day1.txt     # owner: read/write, no one else has access
chmod 644 notes/day1.txt     # owner: read/write, others: read only
```

**Symbolic mode** adds or removes specific permissions:

```bash
chmod +x script.sh           # make a file executable
chmod u+x script.sh          # add execute for the owner only
chmod g-w file.txt           # remove write from the group
```

 7. Superuser and `sudo`

The **root** user is the administrator of the system and has unrestricted access to all files. Running everyday work as root is risky, so Linux provides **`sudo`** (superuser do), which lets an authorized user run a single command with administrator privileges after entering their password.

```bash
whoami                       # shows the current username
sudo ls /root                # list the root user's home directory
```

Since `sudo` bypasses normal restrictions, it should be used only when necessary and only with commands whose effect is understood.

 8. Practical Commands Practiced

```bash
ls -l notes/                 # view permissions
chmod 600 notes/day1.txt     # restrict file to owner only
chmod 644 notes/day1.txt     # restore normal read access
touch script.sh              # create an empty file
chmod +x script.sh           # make it executable
ls -l script.sh              # verify the x permission was added
whoami                       # check current user
sudo ls /root                # access a restricted directory
```

**Observation:** After `chmod +x script.sh`, the permission string changed from `-rw-r--r--` to `-rwxr-xr-x`, showing that execute permission was added.

 9. Summary

- Permissions control who can read, write, or execute a file or directory.
- They are set for three categories: owner, group, and others.
- `ls -l` displays them, and `chmod` changes them using numbers (4, 2, 1) or symbols (`+`, `-`).
- `sudo` grants temporary administrator access and must be used carefully.
-
