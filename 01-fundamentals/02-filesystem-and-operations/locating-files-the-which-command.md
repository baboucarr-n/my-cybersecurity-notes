# Locating Files (the which and whereis commands)

*Date: 12 February 2026*

## The which Command

which searches through the directories listed in your PATH variable and return the first match it find. If you get a different path than expected, don't worry -- it just mean the program is installed somewhere different on your system.

```
which <command>
```

**Checking for multiple installations:** use -a to see if a command is installed in more than one place.

---

## The whereis Command

whereis is used to locate the binary, source, and man page files for a command. Unlike which, it only searches a restricted set of locations, which makes it faster than searching the whole filesystem.

```
whereis <command>
```

Example:
```
whereis cat
```

**Finding binary files** -- use -b:
```
whereis -b grep
```

**Locating man pages** -- use -m:
```
whereis -m ssh
```
Output:
```
ssh: /usr/share/man/man1/ssh.1.gz
```
Confirmed it was real by running:
```
ls /usr/share/man/man1/ssh.1.gz
```

**Combining options:** -bm together give you both the binary and man page location in one go. -s is for finding source files.

---

Also touched on echo and output redirection (>) while going through this one.