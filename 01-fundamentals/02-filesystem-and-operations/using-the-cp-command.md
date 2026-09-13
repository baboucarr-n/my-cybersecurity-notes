# Using the cp Command

*Date: 09 February 2026*

## Copying a Single File

cp is used to copy a file -- give it a source and a target. This creates a copy in the new location while leaving the original file where it was, kind of like copy in Windows. The original stays put after the copy is made.

## Copying Properly

Say I want to copy a file into the projects folder. I need to specify the file I want to copy and where I want to save it.

Steps:
1. Go to the directory where the file is located, using ls ~/projects
2. Then run the copy with the path

Example:
```
cp ~/project/important_report.txt ~/project/important_report_backup.txt
```

- cp -- the command that lets me copy the file
- ~/project/important_report.txt -- the file I'm copying from
- ~/project/important_report_backup.txt -- where I want the duplicate to go

## Copying Multiple Files

Syntax:
```
cp file1 file2 file3 directory/
```

The last argument has to be a directory, because Linux needs one place to put multiple files into.

Example:
```
cp report1.txt report2.txt notes.txt ~/project/text_files/
```

Just list the files you want to copy, then the destination -- and remember the last one always has to be a directory.

## Using Wildcards to Copy Multiple Files (*)

Instead of typing every filename, just use * to grab everything matching a pattern.

Example, copying all text files in a directory:
```
cp *.txt ~/project/backup/
```

## Handling Directories with -r

If you try to copy a directory without -r, it won't work -- Linux throws an error, because a directory isn't a file, it's a container, and copying it safely needs recursion.

So instead:
```
cp -r ~/project/website ~/project/website_backup
```

This copies the website directory and everything inside it into a new website_backup directory.

## cp -t and Why It Exists

Normal order:
```
cp file1 file2 destination/
```

With -t, destination comes first instead:
```
cp -t destination/ file1 file2
```

Tip: use cp -i (interactive) if you want it to ask before overwriting any of the files -- y/n to confirm.

## The Trailing Slash /

When you type something like ~/project/music/, that trailing slash tells Linux explicitly: "this destination is a directory."

## Overwriting vs Copying

After running cp, the original file (favorite_song.mp3 in my case) is still sitting in ~/project. That's the main difference between cp and mv -- cp when you want a duplicate, mv when you actually want to relocate the original. Basically the difference between copy and cut.

## Seeing What's Happening: the -v Option

Use -v (verbose) to see exactly what the command is doing:
```
cp -v favorite_song.mp3 ~/project/music/
```
Output looks something like:
```
'favorite_song.mp3' -> 'music/favorite_song.mp3'
```

## If the Destination Doesn't Exist Yet

If I run:
```
cp favorite_song.mp3 ~/project/new_folder
```
and new_folder doesn't already exist, Linux will just create a new file called new_folder and dump the contents of favorite_song.mp3 into it -- not what you want if you meant to create a folder first.

## Preserving File Attributes with -p

If you want to keep the original file's timestamps and permissions intact when copying, use -p.

## Other Options Worth Knowing

- -u -- only copy if the source is newer, or the destination doesn't exist yet
- -n -- no-clobber, won't overwrite an existing file
- -l -- create hard links instead of actually copying
- -s -- create symbolic links instead of copying

---

*Source: labex.io -- linux cp command lab*