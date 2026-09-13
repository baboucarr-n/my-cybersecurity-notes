# File Searching -- the find Command

As the name suggests, find is used to search for files.

Basic example, searching for a specific file:
```
find . -name "report.txt"
```
Output:
```
./logs/report.txt
```

- find -- the command itself
- . -- start searching from the current directory
- -name "report.txt" -- look for a file exactly named report.txt
- The ./ in the output means "starting from the current directory"

If nothing shows up, it just means the file wasn't found in the current directory or its subdirectories. Might need to search elsewhere, or double check the filename.

## Searching for Multiple File Types

Useful when you need to search for more than one type of file at once:
```
find . -name "*.txt" -o -name "*.log"
```
- find . -- start from current directory
- -name -- specify a filename pattern
- "*.txt" -- anything ending in .txt
- -o -- the "or" operator, same as in programming

## Finding Files by Size

```
find . -type f -size +1M
```
- -type f -- only regular files, not directories or special types
- -size +1M -- files bigger than 1 megabyte

The + means "greater than" -- for exactly 1MB you'd just write 1M, and for less than 1MB you'd write -1M. Other units work too, like k for kilobytes or G for gigabytes. No output means nothing matched that size condition.

find basically answers the question: "where are the files that meet these specific conditions?"

## Finding Recently Modified Files

```
find . -type f -mtime -1
```
-mtime -1 means modified less than 1 day ago. -mtime measures in 24-hour blocks -- exactly 1 day ago would be -mtime 1, more than 1 day ago would be -mtime +1. No output means nothing's been touched in the last 24 hours.

## Executing Commands on Found Files

You can chain find with another command, like running cat on every .txt file it finds:
```
find . -name "*.txt" -exec cat {} \;
```
Breaking it down:
- find . -name "*.txt" -- finds all .txt files, same as before
- -exec cat {} \; -- runs cat on each file found
- {} -- placeholder that gets replaced with each matched filename
- \; -- marks where the -exec command ends (needed so find knows you're not adding more onto it)

## Other Options Worth Knowing

- -user -- find files owned by a specific user
- -group -- find files belonging to a specific group
- -perm -- find files with specific permissions
- -maxdepth / -mindepth -- limit how deep find searches into subdirectories
- -empty -- find empty files or directories
- -newer -- find files newer than a given file