# Problems I Encountered -- grep Wildcard Issue

*Date: 18 February, 2026*

## The Problem

Ran this command:
```
grep -i "User authenticated" ./* > ./task4_output.txt
```
and got an empty output file, even though matches definitely existed.

## Why It Happened

The `./*` wildcard expands to include every file in the current directory -- including `task4_output.txt` itself, since the shell expands the wildcard before grep even runs. Because the output redirection (`>`) truncates the output file first, `task4_output.txt` gets wiped empty before grep gets a chance to actually search and write anything useful into it. So grep ends up trying to search a file that just got emptied out, and the redirection target is the same file it's reading from.

## What I Did

Deleted the output file first, then ran the command again. That worked because the file didn't exist yet when the shell expanded `./*`, so it wasn't part of what grep searched.

## The Cleaner Fix (No Need to Delete Anything)

```
grep -i "User authenticated" ./*.log > task4_output.txt
```
Narrowing the wildcard to just `.log` files avoids catching the output file at all.

Or:
```
grep -i "User authenticated" -- * > task4_output.txt
```
The `--` tells grep "everything after this is a filename, not an option," which also sidesteps the issue in some setups.

Either of these avoids needing to manually delete the file each time.