# Grep Command

*Date: 17 February, 2026*

grep is used for searching and matching patterns in Linux. Stands for "Global Regular Expression Print."

## Basic Search

```
grep "ERROR" theFileName
```
Displays every line containing "ERROR". grep is case-sensitive by default, so this only matches the exact pattern.

## Counting Matches (-c)

```
grep -c "ERROR" theFileName
```
Instead of showing the matching lines, -c just gives a count of how many lines matched.

## Case-Insensitive Search (-i)

```
grep -i "error" theFileName
```
Matches "error", "ERROR", "Error," any case combination. Useful when you're not sure how something was capitalized, or worried about typos.

## Searching Across Multiple Files

```
grep "database connection failed" logs/*
```
The * wildcard means "every file in the logs directory" -- so grep checks all of them without you needing to know exact filenames.

Example output:
```
logs/error.log:[2023-07-02 11:25:40] WARNING: database connection failed, retrying...
logs/server.log:[2023-07-01 10:20:30] ERROR: database connection failed
```

## Using Regular Expressions

```
grep "2023-[0-9][0-9]-[0-9][0-9]" theFileName
```
Breaking it down:
- 2023- -- matches the literal year and hyphen
- [0-9][0-9] -- exactly two digits (month)
- - -- another hyphen
- [0-9][0-9] -- two more digits (day)

Matches any line starting with a 2023 timestamp in that format.

## Displaying Context Around a Match

```
grep -B 2 -A 2 "CRITICAL" theFileName
```
- -B 2 -- show 2 lines before the match
- -A 2 -- show 2 lines after the match

Genuinely useful when troubleshooting -- you don't just get the error line, you get what happened right before and after it.

Shortcut for both at once:
```
grep -C 2 "CRITICAL" theFileName
```
Same result -- 2 lines of context on both sides.

## Inverting the Match (-v)

```
grep -v "ERROR" theFileName
```
Shows everything EXCEPT lines matching the pattern -- basically "give me everything but this."

## Other Options Worth Knowing

- -n -- show line numbers alongside matches
- -r / -R -- recursively search through subdirectories
- -l -- only show filenames that contain a match, not the matching lines themselves
- -w -- match whole words only
- -E -- use extended regex syntax
- -F -- treat the pattern as a fixed string, not a regex

---

*Source: labex.io -- linux grep command pattern searching lab*