*Date: 09 February 2026*

# The mv Command
I see the move command as how we have cut in windows, but with one other capability that the cut did not have in windows did not have, which is also the `mv` commamd also the abiliti to rename a file, so `mv` is the linx xommand that can be use to totally transfer a file without leaving a copy from the orginal location where the file was move from, just like `cut(in windows)` . `AMOTHER FUNCTION, mv has is` you can use the `mv` command to rename a file.
`IN SHORT` mv is the command for moving or renaming files and directories in Linux.

## Moving and Renaming Files

Basic format:
```
mv fileYouWantToMove WhereYouWantToMoveIt/ 
OR mv source distinationFolder
```

## Renaming a File

You can also use mv to rename a file -- if source and destination are in the same directory, Linux just treats it as a rename instead of an actual move.

Example, renaming index.html to home.html:
```
mv index.html home.html
```

- index.html -- the current name (source)
- home.html -- the new name (destination)

Since both are in the same directory, mv knows to rename instead of move.

(source: labex.io -- linux mv command lab)

## Moving Multiple Files at Once

First make a directory to move stuff into:
```
mkdir scripts
```

Then move all .js files into it in one go:
```
mv *.js scripts/
```

- mv -- the command itself
- *.js -- matches any file ending in .js, the * is a wildcard for "any characters"
- scripts/ -- the destination folder

This moves every JavaScript file into scripts in one shot. Can check it worked with ls scripts/ after.

## Using -i for Safer Moves

Good habit -- use -i (interactive) when moving files so it prompts you before overwriting anything that already exists at the destination. Saved me from overwriting stuff by accident more than once.

---

*Linux journey/lab.io was my main source when learnig the mv command*