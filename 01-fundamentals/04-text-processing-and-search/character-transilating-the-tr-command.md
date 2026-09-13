# Character Translating -- the tr Command

*Date: 17 February, 2026*

tr is a flexible command used to convert text at the character level. Short for "translate," it's commonly used for converting case, removing specific characters, and general data cleaning.

## Basic Syntax

```
tr [OPTION]... SET1 [SET2]
```

## Converting Case

```
cat theFileName | tr 'a-z' 'A-Z'
```

- cat theFileName -- reads the file's contents
- | -- pipes that output into the next command
- tr 'a-z' 'A-Z' -- translates each lowercase letter (a-z) to its uppercase equivalent (A-Z)

So if theFileName contains "hello, world," this prints "HELLO, WORLD" to the terminal -- but it doesn't actually change the file itself, just the output shown.

## Deleting Characters

tr can also delete specific characters from input -- useful for cleaning up text.

```
cat theFileName | tr -d '[:punct:]'
```

- cat theFileName -- reads the file
- | -- pipes it into tr
- tr -d '[:punct:]' -- deletes the specified characters

Breaking down -d '[:punct:]':
- -d -- tells tr to delete matched characters
- [:punct:] -- a predefined character class representing all punctuation

This strips out every punctuation character from the text, leaving just letters, numbers, and spaces.

---

*Learned this one from Linux Journey.*