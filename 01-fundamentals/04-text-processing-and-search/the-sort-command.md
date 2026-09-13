# The sort Command

sort is a powerful utility for organizing and arranging text data.

By default, sort works line by line, alphabetically -- it looks at the first character of each line, then the next, and so on, then prints everything back out in alphabetical order.

## Sorting by a Specific Field (Numeric Sort)

Say you have a list of students with their ages:
```
Lamin Jarju:21
Fatou Ceesay:18
Ebrima Sanneh:19
Awa Touray:20
Ousman Bojang:18
```

You want to sort by age instead of alphabetically by name. This command does it:
```
sort -n -t: -k2 theFileName
```

Breaking it down:
- -n -- perform a numeric sort
- -t: -- fields are separated by colons
- -k2 -- use the second field (the age) as the sort key

This sorts the list based on age instead of the name.

Important note: without -n, sort treats the ages as plain strings/text, which gives you a wrong order (something like 18, 19, 20, 21, 3 instead of proper numeric order). -n forces it to actually sort numerically.