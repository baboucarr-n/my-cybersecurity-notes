# File Scrolling with the more Command

more is used to view and navigate large text files.

Syntax:
```
more theFileName
```

Navigation once inside:
- Space -- move to next page
- Enter -- move down one line
- b -- go back a page
- q -- quit and return to the prompt

## Starting From a Specific Line

Since more is mainly for big files, you can jump straight to a line number using +LineNumber, no space:
```
more +100 theFileName 
```
You can use = to confirm the current line number.

## Customizing the Display

Use -n to display a specific number of lines at once:
```
more -5 theFileName
```

## Searching for Specific Data

```
more +/"2023-07-15" theFileName
```
The +/ before the search term tells more to jump straight to the first occurrence of that pattern -- so the file opens right at "2023-07-15" instead of you having to scroll to find it.

## Other Options Worth Knowing

- -d -- shows helpful prompts
- -f -- counts logical lines instead of screen lines
- -p -- clears the screen before displaying each page
- -c -- repaints the screen instead of scrolling
- -s -- squeezes multiple blank lines into one
- -u -- suppresses underlining