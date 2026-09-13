# Problems I Encountered in Labs -- File Discovery Lab

*Date: 15 February 2026*

## The Challenge

Lab: Master the Art of File Discovery (labex.io)

Tasks:
1. Use `which` to find the location of the python3 executable
2. Use `whereis` to find all locations related to the gcc compiler
3. Use `find` to search for all `.conf` files in `/etc` and its subdirectories

Requirements:
- All commands run from `~/project`
- For find, redirect output to a file called `configFiles.txt` inside `~/project`
- Use the right options for accurate results
- find should only match files (not directories) with the exact `.conf` extension

(source: labex.io -- discover critical system resources lab)

## Where I Got Stuck

My problem was with task 3.

Things I tried that didn't work:
```
find . -name "*.conf" | customConfigFile
cd /etc ; find . -name "*.conf"
find . -name "*.conf" | cd /etc
find . -name "*.conf" | cat > configFiles.txt
```

I kept trying to force it through piping (`|`), especially attempts 1 and 4, when really I just needed plain output redirection with `>` instead.

The other issue: I was running `find .` from inside `~/project`, so the `.` meant "start searching from project," but the requirement was to search `/etc`, which is a completely different directory off the home path. Once I realized that, the fix was simple.

## What Actually Worked

```
find /etc -name "*.conf" > ~/project/configFiles.txt
```

Two mistakes stacked on top of each other here -- wrong redirection approach, and searching from the wrong starting directory. Fixing the starting point first made the rest click.