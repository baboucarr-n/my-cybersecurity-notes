HTB notes

31 January 2026

15:49

Â 

The Linux philosophy centers on simplicity, modularity, and openness. It
advocates for building small, single-purpose programs that perform one
task well. These programs can be combined in various ways to accomplish
complex operations, promoting efficiency and flexibility. Linux follows
five core principles:

Â 

*From \<<https://academy.hackthebox.com/module/18/section/94>\>*

Components of linux

| **Component** | **Description** |
|----|----|
| Bootloader | A piece of code that runs to guide the booting process to start the operating system. Parrot Linux uses the GRUB Bootloader. |
| OS Kernel | The kernel is the main component of an operating system. It manages the resources for system's I/O devices at the hardware level. |
| Daemons | Background services are called "daemons" in Linux. Their purpose is to ensure that key functions such as scheduling, printing, and multimedia are working correctly. These small programs load after we booted or log into the computer. |
| OS Shell | The operating system shell or the command language interpreter (also known as the command line) is the interface between the OS and the user. This interface allows the user to tell the OS what to do. The most commonly used shells are Bash, Tcsh/Csh, Ksh, Zsh, and Fish. |
| Graphics server | This provides a graphical sub-system (server) called "X" or "X-server" that allows graphical programs to run locally or remotely on the X-windowing system. |
| Window Manager | Also known as a graphical user interface (GUI). There are many options, including GNOME, KDE, MATE, Unity, and Cinnamon. A desktop environment usually has several applications, including file and web browsers. These allow the user to access and manage the essential and frequently accessed features and services of an operating system. |
| Utilities | Applications or utilities are programs that perform particular functions for the user or another program. |

Â 

*From \<<https://academy.hackthebox.com/module/18/section/94>\>*

Â 

Â 

Linux Architecture

The Linux operating system can be broken down into layers:

| **Layer** | **Description** |
|----|----|
| Hardware | Peripheral devices such as the system's RAM, hard drive, CPU, and others. |
| Kernel | The core of the Linux operating system whose function is to virtualize and control common computer hardware resources like CPU, allocated memory, accessed data, and others. The kernel gives each process its own virtual resources and prevents/mitigates conflicts between different processes. |
| Shell | A command-line interface (**CLI**), also known as a shell that a user can enter commands into to execute the kernel's functions. |
| System Utility | Makes available to the user all of the operating system's functionality. |

Â 

*From \<<https://academy.hackthebox.com/module/18/section/94>\>*

Â 

File System Hierarchy

The Linux operating system is structured in a tree-like hierarchy and is
documented in theÂ [Filesystem
Hierarchy](http://www.pathname.com/fhs/)Â Standard (FHS). Linux is
structured with the following standard top-level directories:

<img src="../..//image3.png"
style="width:8.29167in;height:5.33333in"
alt="Diagram of Linux file system hierarchy with root directory branching to folders: /bin, /boot, /dev, /etc, /lib, /media, /mnt, /opt, /home, /run, /root, /proc, /sys, /tmp, /usr, /var." />

| **Path** | **Description** |
|----|----|
| / | The top-level directory is the root filesystem and contains all of the files required to boot the operating system before other filesystems are mounted, as well as the files required to boot the other filesystems. After boot, all of the other filesystems are mounted at standard mount points as subdirectories of the root. |
| /bin | Contains essential command binaries. |
| /boot | Consists of the static bootloader, kernel executable, and files required to boot the Linux OS. |
| /dev | Contains device files to facilitate access to every hardware device attached to the system. |
| /etc | Local system configuration files. Configuration files for installed applications may be saved here as well. |
| /home | Each user on the system has a subdirectory here for storage. |
| /lib | Shared library files that are required for system boot. |
| /media | External removable media devices such as USB drives are mounted here. |
| /mnt | Temporary mount point for regular filesystems. |
| /opt | Optional files such as third-party tools can be saved here. |
| /root | The home directory for the root user. |
| /sbin | This directory contains executables used for system administration (binary system files). |
| /tmp | The operating system and many programs use this directory to store temporary files. This directory is generally cleared upon system boot and may be deleted at other times without any warning. |
| /usr | Contains executables, libraries, man files, etc. |
| /var | This directory contains variable data files such as log files, email in-boxes, web application related files, cron files, and more. |

Â 

*From \<<https://academy.hackthebox.com/module/18/section/94>\>*

Â 

Â 

Terminal Emulators

Terminal emulation is software that emulates the function of a terminal.
It allows the use of text-based programs within a graphical user
interface (GUI).Â 

Â 

*From \<<https://academy.hackthebox.com/module/18/section/65>\>*

Â 

The home directory for a user is marked with a tilde \<~\> and is the
default folder when we log in.

Â 

*From \<<https://academy.hackthebox.com/module/18/section/66>\>*

Â 

Â Â Prompt Description

\<username\>@\<hostname\>\[~\]\$

The dollar sign, in this case, stands for a user. As soon as we log in
asÂ root, the character changes to aÂ hashÂ \<#\> and looks like this:

**TheÂ PS1Â variable** in Linux systems controls how your command prompt
looks in the terminal. It's like a template that defines the text you
see each time the system is ready for you to type a command. By
customizing the PS1 variable, you can change the prompt to display
information such as your username, your computer's name, the current
folder you're in, or even add colors and special characters. This allows
you to personalize the command-line interface to make it more
informative or visually appealing.

Â 

Â 

Â 

Â 

*From \<<https://academy.hackthebox.com/module/18/section/66>\>*

Â 

Â 

Â 





