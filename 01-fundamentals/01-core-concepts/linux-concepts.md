# Linux Concepts

*Date: 24 January 2026*

## Core Terms

- **Distribution (distro):** A full Linux setup built around the Linux kernel, bundled with a set of software and tools. Different distros (Kali, Ubuntu, Parrot) package things differently but the kernel underneath is the same.
- **Binary:** An executable file -- same idea as a `.exe` on Windows, just without the extension.
- **Directory:** Linux's word for a folder in windowa. Directories are organized in a tree, starting from root. Base on different opreation each of the directories plays in the over linux file system.
- **Home:** Every user gets a `/home/username` directory. Anything you create usually goes to here here by default.

- **Kali:** Is A Linux distro built specifically for penetration testing -- comes pre-loaded with security tools. It is also super popular thou.

- **Root:** The superuser/admin account. Root can do anything on the system -- add users, change passwords, reconfigure the whole machine. This is the account you don't want to be careless with. That is why I do not login as root when parforming regular daialy task. In a linux system root is God lol...

- **Script:** A set of commands written to run together in sequence, interpreted line by line. A lot of hacking tools are just scripts under the hood. Scripts also perform a specific task, base on how you write your script, you can use  different programming language to write you own scriipts -- just whatever programming language you know and confortable with the most. Most common I observe for pentestings is python because of it easy to understand synthax.

- **Shell:** The interpreter that takes the commands you type and translates them into something the kernel can actually execute. I use to miss this concept, I just it was the same as a terminal but it is different, and you can use differnt shells I found out, like bash shell or zsh...

- **Terminal:** The command-line interface itself -- the window you type into.

**Shell vs Terminal:** The shell is the interpreter doing the translating (your commands -> binary the kernel understands). The terminal is just the window/interface you use to type those commands in.

---

## Absolute Paths vs Relative Paths (and why permissions kept failing on me)
Honestly this concept I really use to mis inteprete but after rasing few sources the concepts becames clear to me, and here is how i understands it to be, and this is what it is:

- **Absolute path** -- starts with `/`. Always points to the same place, so root-owned top-level dirs give **Permission denied** to a normal user.

- **Relative path** -- doesn't start with `/`. Interpreted relative to your current location. Works fine inside your own home directory.

**What actually happened to me:** I kept typing absolute paths even after `cd ~`, so it read as "create this under root" -- instant denial. Switched to relative paths and it worked.

(A separate "File exists" error is just a name collision, unrelated to permissions.)

---

## Piping

Piping (`|`) connects the output of one command straight into the input of another, letting you chain commands instead of running each step manually.

---

*Learning some of the concepts from Linux Journey -- cross-referencing with Linux Basics for Hackers when it gets fuzzy.*
