# File End Display (the tail command)

tail is a command in Linux used to display the last lines of a text file.

Syntax:
```
tail theFileName
```
By default, tail shows the last 10 lines of the file.

## Customizing the Number of Lines (-n)

You can customize how many lines you want to see:
```
tail -n 5 theFileName
```
This shows the last 5 lines instead of the default 10.

## Viewing Content From a Specific Line

You can start the display from a specific line using +LineNumber:
```
tail -n +50 theFileName
```
The -n +50 tells tail to start displaying from the 50th line onward, all the way to the end of the file.

---

*Source: labex.io -- linux tail command lab*