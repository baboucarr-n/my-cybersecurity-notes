# Standard Input and Standard Output (stdin/stdout)

*Date: 04 April 2026*

## Everything in Linux Is a File

Even the screen and the keyboard are treated as files in Linux -- these are called streams. When the machine starts up, these stream files are what let input/output actually work across the whole system.

Standard input (stdin) is where whatever you type into the terminal gets sent -- the shell reads from stdin to figure out what command to run.

**Correction I caught myself making here:** these files don't "run" -- they're static interfaces that programs open as file descriptors (0, 1, 2) at startup. Also, stdin doesn't only come from the keyboard -- it can come from a file (via `<`) or from another program's output (via a pipe, `|`).

(source: BSD Library Functions Manual -- STDIN(3), via learnlinux.org.za)

## The Basics of stdin and stdout

Every command-line process has at least two core streams: stdin (what it reads in) and stdout (what it writes out as results).

```
echo HelloWorld > newFile.txt
```
Here echo generates output, and `>` redirects that output into a file called `newFile.txt`.

**Correction I caught myself making here too:** `>` doesn't "display" into the file -- it redirects and saves into it. Displaying only happens on the screen. Once `>` is used, stdout never actually reaches your eyes -- it gets captured straight into the file instead.

(source: labex.io -- stdin standard in redirect lesson)

## Redirecting stdout

`>` redirects standard output into a file or another destination -- but it **overwrites** whatever's already in that file, wiping out the previous content.

To avoid that, use `>>` (append) instead -- this adds new content to the file while keeping what was already there.

Example 1 -- overwrite:
```
echo helloWorld > newFile.txt
```

Example 2 -- append:
```
echo helloWorld >> newFile.txt
```

## Redirecting stdin

*(Still need to go through this properly -- didn't get to it in this note yet.)*