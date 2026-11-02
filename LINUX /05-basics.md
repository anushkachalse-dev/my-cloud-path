# Group Management & User Creation with useradd

 1. Introduction
In a multi-user system, administrators rarely set permissions for each user one by one. Instead, users are placed into groups, and permissions are given to the group. Today's practice focused on creating groups, creating users with `useradd`, and assigning them to those groups.

 2. Creating a Group: `groupadd`
The `groupadd` command creates a new group. Each group gets a unique Group ID (GID), and group details are stored in `/etc/group`.

Groups make access control easier. For example, all developers can be added to a `developers` group, and that group can be given access to shared project files.

 3. Creating a User: `useradd`
`useradd` is a low-level command for creating a user account. Unlike `adduser`, it is not interactive. It does only what the given options tell it to do.

| Option | Purpose |
|--------|---------|
| `-m` | Create the home directory |
| `-g` | Set the primary group |
| `-G` | Add the user to secondary groups |
| `-s` | Set the login shell |

Without `-m`, many systems will not create a home directory.

 4. adduser vs useradd
| Feature | `adduser` | `useradd` |
|---------|-----------|-----------|
| Type | Interactive, friendly script | Low-level utility |
| Home directory | Created automatically | Needs the `-m` option |
| Password prompt | Yes | No, set separately |
| Best for | Manual, everyday use | Scripts and automation |

 5. Primary and Secondary Groups
- **Primary group:** the main group of a user. Files the user creates belong to it by default.
- **Secondary groups:** additional groups that give the user extra access.

 6. Setting a Password: `passwd`
A user created with `useradd` has no usable password until one is set. The `passwd` command sets or changes it. Passwords are stored as hashes in `/etc/shadow`, not as plain text.

 7. Verifying with `id`
The `id` command shows the user's UID, primary GID, and all group memberships. It is used to confirm that the user was added to the correct groups.

 8. Home Directories and Ownership
Each user's home directory is usually `/home/username`, and it is owned by that user. Ownership decides who can read, write, or execute files inside it. This is how Linux keeps one user's files separate from another's.

 9. Important Files
| File | Contents |
|------|----------|
| `/etc/passwd` | User account information |
| `/etc/shadow` | Encrypted passwords |
| `/etc/group` | Group information |

 10. Conclusion
Groups simplify access control, and `useradd` gives precise control over how accounts are created. Together with `passwd` and `id`, they form the core of user and group management on a Linux system.
