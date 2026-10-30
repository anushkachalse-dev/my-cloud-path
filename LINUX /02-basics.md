# Linux File System:

 1. Introduction to File System

A **file system** is the method and data structure an operating system uses to store, organize, and manage data on a disk or partition. It consists of **files**, **directories**, and the **permissions** associated with them. Data is stored in a **hierarchical (tree-like) structure** of directories and files, where every file can be reached through a unique path.

 2. Path Format

A path describes the location of a file or directory in the file system.

- **Windows** uses a drive letter and backslashes. Example: `C:\Program Files\Java`
- **Linux** uses forward slashes and starts from a single root directory `/`. Example: `/etc/folder`

Unlike Windows, Linux has no drive letters. All storage devices are attached (mounted) under the single root tree.

 3. Types of File Systems

A file system type defines how data is laid out and managed on a disk. Common types in Linux:

1. **ext3** - An older Linux file system that introduced journaling, which protects data from corruption after a crash.
2. **ext4** - The successor of ext3 and the default on many distributions. It supports larger files and volumes and offers better performance.
3. **XFS** - A high-performance journaling file system, well suited for large files and large storage systems.
4. **Btrfs (B-tree File System)** - A modern file system based on B-trees. It supports snapshots, checksums, and built-in volume management.
5. **FAT** - A simple file system with wide compatibility across operating systems. Commonly used on USB drives and memory cards.

 4. Checking the File System

The file system of a Linux machine can be inspected in three ways:

1. `lsblk -f` - Lists block devices (disks and partitions) along with their file system type.
2. `df -Th` - Shows mounted file systems, their type, size, and used and available space in human-readable form.
3. `cat /etc/fstab` - Displays the configuration file that defines which file systems are mounted automatically at boot.

 5. Inode

An **inode** (index node) is a data structure used by Linux file systems to store **metadata** about a file or directory. It does not store the file's actual content.

**How it works:** Every file is identified by an **inode number**. The file system uses this number to locate the inode. The inode in turn contains **pointers** to the **data blocks** on disk where the actual file data is stored.

```
File name -> Inode number -> Inode (metadata + pointers) -> Data blocks
```

**Metadata held in an inode** includes the file's permissions, owner and group, size, timestamps, link count, and the pointers to its data blocks. The file name itself is stored in the parent directory entry, not in the inode.

 6. Linux Directory Structure

Linux follows a standard hierarchy, with `/` (root) at the top. Each directory has a defined purpose.

- **`/bin`** - Contains essential user binaries (executable programs), such as common commands like `ls` and `cp`.
- **`/etc`** - Holds system configuration files, for example for users, network, services, and system applications.
- **`/home`** - Contains the personal directories of all regular users.
- **`/root`** - The home directory of the root user (the system administrator).
- **`/var`** - Stores variable data, which changes frequently, such as logs and databases.
- **`/tmp`** - Holds temporary files created by the system and by users.
- **`/boot`** - Contains the files required for system boot-up, including the Linux kernel and the initial RAM disk image.

 7. Summary

- A file system organizes data on disk as a hierarchy of files and directories with permissions.
- Linux uses a single root `/` and forward slashes in paths.
- Common types are ext3, ext4, XFS, Btrfs, and FAT.
- An inode stores a file's metadata and points to the data blocks holding its content.
- Each standard directory (`/bin`, `/etc`, `/home`, `/root`, `/var`, `/tmp`, `/boot`) has a specific role.
