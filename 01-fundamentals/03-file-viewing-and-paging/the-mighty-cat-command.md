# The Mighty cat Command :)

cat is a versatile command for viewing and manipulating data.

You can use it to combine the contents of two files. Say file1.txt has "hello" and file2.txt has "Baboucarr" -- running:
```
cat file1.txt file2.txt
```
gives you:
```
hello
Baboucarr
```

## Output Redirection

There's a concept in Linux called output redirection. Instead of a command's output just printing to the terminal, you can send it into a file instead, using the > symbol.

Basically it lets you control where input comes from and where output goes -- read from a file instead of typing manually, or filter/modify output from multiple commands. Gives a lot of flexibility over how data flows.

Example:
```
cat sales.txt marketing.txt > combined_report.txt
```
- cat sales.txt marketing.txt -- displays both files' contents like before
- > -- instead of printing to the terminal, this writes the output into a file
- combined_report.txt -- the new file being created

So this command basically says: take the combined contents of sales.txt and marketing.txt, and instead of showing it to me, dump it into a new file called