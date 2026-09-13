# Linux nl Command: Line Numbering

nl is a command used for numbering lines in text files.

Syntax:
```
nl theFileName
```
This numbers the file nicely, easy to reference stuff and makes it easier when discussing with colleagues.

## Numbering All Lines Including Blank Ones

Sometimes you want every single line numbered, blank ones too. Use -b a for that.

```
nl -b a theFileName
```

- -b controls how the body of the file gets numbered
- a means "all" -- number every line, including the blank ones

## Customizing the Number Format

nl also let you customize how the line numbers actually look. Useful for readability or prepping output for something else. Let's right-align the numbers and add leading zeros:

```
nl -n rz theFileName
```

Breaking down -n rz:
- -n sets the numbering format
- r means right-aligned (which is actually the default anyway)
- z adds the leading zeros

## Numbering Specific Line Types

nl can also number only specific types of lines, useful when working with a messy file and you only care about certain lines.

Say I want to number only non-empty lines that don't start with a # (since # is usually a comment in config files):

```
nl -b p'^[^#]' theFileName
```

Breaking that pattern down:
- -b p tells nl to only number lines matching a pattern
- ^[^#] is the regex -- ^ means start of line, [^#] means any character that isn't #
- So together it matches any line where the first character isn't a #

## Combining Options for Complex Numbering

```
nl -b a -n rz -s ': ' -w 3 theFileName
```

- -b a -- number all lines, blanks included
- -n rz -- right-align with leading zeros
- -s ': ' -- use ': ' as the separator between number and content
- -w 3 -- set the number field width to 3 characters

## Other Options Worth Knowing

- -v NUM -- start numbering at NUM instead of 1
- -i NUM -- increment by NUM instead of 1
- -l NUM -- group NUM lines together and only number the first line of each group
- -f a -- number all header lines (before the first body line)