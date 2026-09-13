# The wc Command

*Date: 16 February 2026*
wc is a powerful Linux utility for counting words, characters, and lines in a text file.

## Counting Lines

Use -l to count lines:
```
wc -l theFileName
```

## Counting Words

Use -w to count words:
```
wc -w theFileName
```

## Counting Characters

Use -m to count characters:
```
wc -m theFileName
```

If a file comes back with a large character count, it might be a sign the file's doing too much -- worth considering whether it should be split into smaller, more focused pieces.

## Combining Options

You can combine flags to get lines, words, and characters all at once:
```
wc -l -w -m theFileName
```

Example output:
```
121 284 8388 theFileName
```
The numbers correspond to the order of the options given -- lines, words, characters.