# Text Sorting -- the sort Command

*Date: 16 February, 2026*

sort is a powerful utility for arranging and organizing text files.

## How sort Works

sort reads a file line by line and rearranges those lines into a specific order -- usually alphabetical or numerical. By default it sorts alphabetically, A to Z, comparing character by character.

```
cat theFileName
```

## Sorting by Age (Numeric Values)

Say we have a student list like:
```
Lamin Jarju:21
Fatou Ceesay:18
Ebrima Sanneh:19
Awa Touray:20
Ousman Bojang:18
```

To sort by age instead of name:
```
sort -n -t: -k2 theFileName
```

- -n -- numeric sort
- -t: -- fields separated by colons
- -k2 -- use the second field (age) as the sort key

Result, sorted youngest to oldest:
```
Fatou Ceesay:18
Ousman Bojang:18
Ebrima Sanneh:19
Awa Touray:20
Lamin Jarju:21
```

Without -n, sort treats the numbers as plain characters/strings, which can give a wrong order.

## Reverse Sorting

```
sort -nr -t: -k2 theFileName
```

- -n -- numeric sort
- -r -- reverse order (descending instead of ascending)
- -t: -- colon delimiter, same idea as -d
- -k2 -- sort by the second field

Displays the list in reverse order.

## Sorting by Multiple Fields

```
sort -t: -k2n -k3nr theFileName
```

- -t: -- colon delimiter
- -k2n -- sort by field 2 (age) numerically, ascending
- -k3nr -- then sort by field 3 (grade) numerically, descending, as a tiebreaker

This sorts primarily by age (ascending), and when ages match, breaks the tie by grade (descending).

Example, before:
```
Lamin Jarju:21:87
Fatou Ceesay:18:92
Ebrima Sanneh:19:95
Awa Touray:20:88
Ousman Bojang:18:91
```

After:
```
Fatou Ceesay:18:92
Ousman Bojang:18:91
Ebrima Sanneh:19:95
Awa Touray:20:88
Lamin Jarju:21:87
```

This is called multi-key sorting -- genuinely useful when working with multiple records or database-style data. Here we're grouping by age first, then ranking by grade within each age group.

(source: labex.io -- linux sort command lab)

## Removing Duplicates

```
sort -u theFileName
```
Does exactly what it says -- removes duplicate lines.

## Other Options Worth Knowing

- -f -- ignore case when sorting
- -b -- ignore leading blanks
- -c -- check if the input is already sorted
- -o -- write output to a file instead of standard output