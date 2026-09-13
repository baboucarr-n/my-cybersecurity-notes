# File Displaying -- the head Command

head is used for displaying contents of a file, but it only shows the first 10 lines by default.

Syntax:
```
head theFileName
```

## Customizing the Number of Lines (-n)

Sometimes 10 lines is too many or too few, so you can specify how many you want:
```
head -n 5 theFileName
```
This shows only the first 5 lines.

## Viewing Multiple Files at Once

Handy as a sysadmin when you want to quickly glance at several files at the same time:
```
head access.log error.log
```

## Using head with Pipes

head works well combined with other commands through piping.

Say you want to see the first 3 lines of a