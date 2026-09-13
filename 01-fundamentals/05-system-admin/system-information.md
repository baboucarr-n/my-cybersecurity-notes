# System Information

When working with Linux systems, it's important to be able to quickly pull key info -- system details, running processes, network config, users, and directory structure. Below are commands that help with that.

| Command | Description |
|---|---|
| whoami | Shows the current username |
| id | Returns the user's identity (UID, GID, groups) |
| hostname | Sets or prints the current host's name |
| uname | Prints basic OS and hardware info |
| pwd | Returns the current working directory |
| ifconfig | Assigns/views network interface addresses and settings |
| ip | Shows or manipulates routing, network devices, interfaces, tunnels |
| netstat | Shows network status |
| ss | Investigates sockets (newer alternative to netstat) |
| ps | Shows process status |
| who | Shows who's currently logged in |
| env | Prints environment variables, or runs a command in a modified environment |
| lsblk | Lists block devices |
| lsusb | Lists USB devices |
| lsof | Lists open files |
| lspci | Lists PCI devices |

(source: HackTheBox Academy)

## The id Command

Returns the user's identity and group memberships.
```
id
```
Example output:
```
uid=1000(batista) gid=1000(batista) groups=1000(batista),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),100(users)
```

Breaking this down: `uid` is the user's unique ID number, `gid` is their primary group ID, and `groups` lists every group they belong to (adm, cdrom, sudo, dip, plugdev, users in this case -- each grants different system permissions, like sudo letting you run commands as root).

**What the numbers actually mean:** every user and group on the system gets assigned a number (UID/GID). The system tracks users internally by these numbers, not by username -- the username is really just a human-friendly label mapped to that number. That's why you sometimes see a raw number instead of a name if a user account gets deleted but their files remain.

## Logging in via SSH

SSH (Secure Shell) is a protocol that lets you access and run commands on a remote machine securely.

## The uname Command

Prints system information -- useful for quickly identifying details about a machine.
```
uname
```

**-a** -- prints all available system details at once (kernel name, version, architecture, hostname, etc), all in one line.

**-r** -- shows the kernel release version specifically. Useful for quickly checking if a machine might be vulnerable to a known kernel exploit.
```
uname -r
```

**-m** -- shows the hardware/machine architecture (e.g. x86_64).
```
uname -m
```

## Finding the Home Path

```
echo $HOME
```
