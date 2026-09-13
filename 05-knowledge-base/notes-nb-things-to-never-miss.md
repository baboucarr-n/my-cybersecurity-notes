# Notes (NB) -- Things to Never Miss

*Date: 09 February 2026*

## Quick Things Worth Remembering

Checking attributes of a file/directory:
```
ls -l theFileName
```

Preserving attributes (timestamps, etc) while copying:
```
cp -p theFileName destination
```

Adding a string to a file with echo:
```
echo "Test content" > theFileName.txt
```

Additional mv options worth knowing:
- -f -- force move, no confirmation prompt
- -n -- don't overwrite an existing file
- -v -- verbose, shows what's being done

## Working Directory

*Date: Tuesday, 10 February 2026*

The working directory (or current working directory, CWD) is wherever you currently are in the filesystem. Commands operate relative to this directory by default, unless you give an absolute path instead.

## Piping (need to double check this one)

A pipe redirects the standard output of one command straight into another command as input, letting you chain commands together for further processing. Used a lot in Linux and other Unix-like systems.

Pipes are unidirectional -- data only flows left to right.

## Binary Files

Binary files are the actual executable programs that run when you type a command.

You can use `whereis` to find the binary source file behind a command -- that binary is what actually runs when the command executes.

## Output Redirection

Instead of a command's output printing to the terminal, you can redirect it into a file using `>`.

