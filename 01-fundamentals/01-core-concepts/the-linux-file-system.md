# The Linux File System

*Date: 24 January 2026*

The Linux file system is basically how Linux organize and store data. Everything sit in a tree structure that start from a single root directory, written as /.

- Every file and directory branch off from that one root /
- It's a hierarchical tree, so once you get the logic it's pretty easy to navigate
- Directories like /home, /etc, /bin, /var each have their own specific job on the system
- Linux can run on different file system types too, like ext4, XFS, Btrfs

(reference: geeksforgeeks.org -- linux file hierarchy structure)

---

When you create a file in Linux, it first get stored in RAM. The OS tells you the file was created right away, but the actual write to disk happen later through something called write-back caching.

So it's reliability first (Windows) vs performance first (Linux).

---

## The Main Directories

- **/root** -- home directory for the root user
- **/etc** -- config files, controls how and when programs start up
- **/home** -- where user home directories live
- **/mnt** -- where other filesystems get mounted
- **/media** -- where CDs, USBs usually get mounted
- **/bin** -- application binaries
- **/lib** -- shared libraries, similar idea to DLLs on Windows

---

## / vs ~ (the thing that kept messing me up)

**/ (root)** = the whole building. Only the landlord (root user) can change or add stuff here. I can look around, but can't touch anything → Permission denied.

**~ or /home/batista** = my own bedroom. I'm the boss of everything in there -- create, delete, rename, no permission issues.

So basically: experiment in my bedroom (cd ~), don't try to renovate the whole building (/).