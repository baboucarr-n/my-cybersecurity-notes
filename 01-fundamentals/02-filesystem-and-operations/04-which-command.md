# Locating Files (the which and whereis commands)

## The which Command

`which` searches through the directories listed in your `PATH` environment variable and returns the first match it finds. If you run it on something like Python and get a path you weren't expecting, don't worry -- it just means it's installed somewhere different on your system than you assumed.

Usage:
```
which <command-or-utility>
```

**Multiple installations:** use `-a` to check if a command is installed in more than one location -- useful when you're not sure which version is actually running.

---

## The whereis Command

`whereis` locates the binary, source, and man page files for a command. Unlike `which`, it only searches a restricted set of standard locations (binary directories, library directories, man page directories), which makes it faster than a full filesystem search.

Syntax:
```
whereis <command>
```

Example:
```
whereis cat
```

**Finding binary files** -- use `-b`:
```
whereis -b grep
```
This shows the location of the actual binary that gets executed when you run `grep`.

**Locating man pages** -- use `-m`:
```
whereis -m ssh
```
Output:
```
ssh: /usr/share/man/man1/ssh.1.gz
```
That's the path to ssh's manual page. I confirmed it was real by running:
```
ls /usr/share/man/man1/ssh.1.gz
```
and the file showed up, so the man page does exist on the system.

This is a genuinely useful check as a sysadmin -- you can quickly verify whether documentation for a command actually exists on the box, without opening `man` itself.

**Combining options:** `-bm` together gives you both the binary location and man page location for a utility in one shot. There's also a `-s` option for finding source files specifically.

---

I also touched on `echo` and output redirection (`>`) while working through this.# Locating Files (the which and whereis commands)

## The which Command

`which` searches through the directories listed in your `PATH` environment variable and returns the first match it finds. If you run it on something like Python and get a path you weren't expecting, don't worry -- it just means it's installed somewhere different on your system than you assumed.

Usage:
```
which <command-or-utility>
```

**Multiple installations:** use `-a` to check if a command is installed in more than one location -- useful when you're not sure which version is actually running.

---

## The whereis Command

`whereis` locates the binary, source, and man page files for a command. Unlike `which`, it only searches a restricted set of standard locations (binary directories, library directories, man page directories), which makes it faster than a full filesystem search.

Syntax:
```
whereis <command>
```

Example:
```
whereis cat
```

**Finding binary files** -- use `-b`:
```
whereis -b grep
```
This shows the location of the actual binary that gets executed when you run `grep`.

**Locating man pages** -- use `-m`:
```
whereis -m ssh
```
Output:
```
ssh: /usr/share/man/man1/ssh.1.gz
```
That's the path to ssh's manual page. I confirmed it was real by running:
```
ls /usr/share/man/man1/ssh.1.gz
```
and the file showed up, so the man page does exist on the system.

This is a genuinely useful check as a sysadmin -- you can quickly verify whether documentation for a command actually exists on the box, without opening `man` itself.

**Combining options:** `-bm` together gives you both the binary location and man page location for a utility in one shot. There's also a `-s` option for finding source files specifically.

---

I also touched on `echo` and output redirection (`>`) while working through this.