COMMANS LINE

24 January 2026

20:57

 

- THE MAN PAGES --\> type man a command. To access the manual pages for
  that specific command.

- **man -k** (or apropos) followed by the command shows a list of man
  pages containing a string.

- **Whatis** ---- To see just the description of a manual page, use
  whatis followed by a string.

- **Whereis ----\>** We use whereis to find the location of a particular
  file/ mostly command on the linux file system.

 

 

 

- The **whoami** command--- this command tell us the actual user that is
  current login the system… -- in linux we have the **nomal user** or
  the **root** user so you can get lost as to the current user login, so
  to confirm the actual user using the system, you use the whoami
  command to see

- pwd (Print Working Directory)-- this also tell us where in the file
  system the user is currently in.

>  
>
>  
>
> **<u>WORKING WITH DIRECTORIES</u>**
>
>  
>
> **CHANGING DIRECTORIES**
>
> CHANGING DIRECTORIES WITH cd; this command we can change our current
> directory.
>
> Basically we can use the cd + /+ any directory in out file system and
> we will go to that directory. We are basically changing the directory
> from the root directory to our disired directory…
>
> Example…
>
> batista@DESKTOP-90VKIL2:~\$ cd /etc
>
> batista@DESKTOP-90VKIL2:/etc\$
>
>  
>
> Cd .. This command will take us one step back basically the parent
> directory(the directory above us). ALSO
>
> We can move as many steps as we disired, for example
>
> •         You would use .. to move up one level.
>
> •         You would use ../.. to move up two levels.
>
> •         You would use ../../.. to move up three levels, and so on.
>
> So, for example, to move up two levels, enter cd followed by two sets
> of
>
> double dots with a forward slash in between
>
> Cd - will take us back to where we came from… Basically this command
> will take us to our previous directory
>
> ALSO the cd command alone will take us to the home directory i.e. ~
>
>  
>
> ABSOLUT AND RELATIVE PARTHS
>
> An absolute path is the full path from root (/). A relative path is
> dependant on your current directory.

*From
\<<https://www.reddit.com/r/bash/comments/1cedn73/what_is_the_difference_between_absolute_and/>\>*

> BASICALLY the absolute path show us the exact file location from the
> root directory(/) where as the relative path shows us our current
> directory.
>
>  
>
> Path completion: the tab key can let us with completing the correct
> path we intent top command.
>
>  
>
> **The mighty ls command**
>
> **We us the ls command to list the content of a directory**
>
> ls - a --this command is use to show all the files. This commans also
> includes the hidden files as well…
>
> ls -l will list the content of a directory but in a different format,
> that is it will give all directories in a long listing
>
> Ls -h -- this will present a list in a more readable format. It can be
> combine with the -l .. For example ls -l -h
>
> Any command + --help ---- use this to find a help about that command,
> application.
>
>  
>
>  
>
> **Finding stuff**
>
>  
>
> One of the commands one can use is the locate command, we can use this
> to find the location of a file/application/command etc.. in linux.. It
> has its disadvantages
>
>  
>
>  
>
>  
>
>  
>
> The mkdir command --- we can use the mkdir command to make our own
> directories…. Use the mkdir follwed by the name of the new directory
> you wish to create.
>
> Mkdir + newDirectoryName
>
> Mkdir - p --\> Here we are creating a commanding and specifying the
> exact location where we want the file to be
>
> When given the option -p, then mkdir will create parent directories as
> needed.
>
> paul@debian8:~\$ mkdir -p mydir2/mysubdir2/threedirsdeep
>
> paul@debian8:~\$ cd mydir2
>
> paul@debian8:~/mydir2\$ ls -l
>
>  
>
> rmdir ---\>this command is use to remove a directory when you specify
> the exact directory you want to delete --- when the directory is empty
>
> rmdir -p ---\> and similar to the mkdir -p option, you can also use
> rmdir to recursively remove
>
> directories.
>
>  
>
> DATE: 2nd February, 2026
>
> **rmdir -p** means **remove directory (and its parent directories) if
> they become empty** — similar to how mkdir -p creates parent
> directories as needed.
>
> **Short explanation + example**
>
> \# First create nested folders (like in your example)
>
> mkdir -p test42/subdir
>
> \# → creates: test42/ and inside it: subdir/
>
>  
>
> \# Now remove the deepest one + clean up empty parents
>
> rmdir -p test42/subdir
>
>  
>
>  
>
> **WORIKING WITH FILES**
>
> Points
>
> ----\> All files are case sensitive
>
> -----\> Everything is a file:
>
> A directory is a special kind of file, but it is still a (case
> sensitive!) file. Each terminal
>
> window (for example /dev/pts/4), any hard disk or partition (for
> example /dev/sdb1) and
>
> any process are all represented somewhere in the file system as a
> file. It will become clear
>
> throughout this course that everything on Linux is a file.
>
>  
>
>  
>
> The file command/utility in linux -- this is use to determine the type
> of a file by exermining its content.
>
> **Main purpose**

- It tells you what kind of data is inside a file: text, image,
  executable, PDF, ZIP archive, directory, empty file, etc.

>  
>
> DESCRIPTION
>
> This manual page documents the format of magic files as used by the
> file(1) command, version 5.45. The file(1) command identifies the type
> of a file
>
> using, among other tests, a test for whether the file contains certain
> “magic patterns”. The database of these “magic patterns” is usually
> located in
>
> a binary file in /usr/share/misc/magic.mgc or a directory of source
> text magic pattern fragment files in /usr/share/misc/magic. The
> database specifies
>
> what patterns are to be tested for, what message or MIME type to print
> if a particular pattern is found, and additional information to
> extract from the
>
> file.
>
>  

- **touch**

> One way to create an empty file is through the using of the touch
> command.
>
> The touch -- date="Add the date here(e.g February 4, 2026 10:45 PM)" +
> the name of the file ----\> here we will create a file and add a date
> of string
>
> The touch -t ----\> this touch -t 203001011200 + future-plan.txt with
> the -t we can create a file and ass a timestamp to the file.
>
>  
>
>  
>
> Remove forever
>
> ---\> rm this command will delete files permanently with no recycly
> bin/trash by default
>
> rm \[options\] file(s) or directory(s)
>
> We can use the -I option to prevent ourself from accidentally removing
> a file, you can type rm -i.
>
> The rm -rf statement is famous because
>
> it will erase anything (providing that you have the permissions to do
> so). When you are logged on as root, be very careful with rm -rf (the
> f means force and the r means recursive) since being root implies that
> permissions don't apply to you. You can literally erase your entire
> file system by accident.
>
>  
>
> DATE: Thursday February 5th, 2026. 18:00
>
> Copy one file
>
> The cp command ---\> To copy a file use the cp command with a source
> and a target. -- this will create copy of a file in a new location by
> leaving the old file in it place just like in windows.. The file will
> remains in it's place after creation.
>
> DATE: February 9, 2026. 15:02
>
> So basically the copy command is a way of duplicating
> directories/files in linux
>
>  
>
> Properly using the cp command
>
> Let's say we want to copy a file in the projects folder; to do so we
> need to specify the file I want to copy and where I want to save it
> basically. This is exactly what to do
>
> Steps
>
> Step1--\> head to the the directory where the file you want to copy is
> located using ls ~/projects
>
> Step2 ---\> the you can use the parth where the file is cp
> ~/project/important_report.txt ~/project/important_report_backup.txt
>
> cp ---\> this is command that allow me to copy the file
>
> ~ ---\> this we are saying the file located at the home directory
>
> /project/important_report.txt --\> we are the file I want to copy from
> here
>
> /project/important_report_backup.txt---\> and here's is where I want
> to put the duplicate file.
>
> **HOW TO COPY MULTIPLE FILES**
>
> To copy multiple files at once, the syntax is:
>
> cp file1 file2 file3 directory/
>
> The last argument must be a directory. Why? Because Linux needs **one
> place** to put **multiple files**.
>
> For example
>
> cp report1.txt report2.txt notes.txt ~/project/text_files/
>
> Basically just state the files you wish to copy and give it it's
> destination but make sure you specifying it's destination just give it
> a the path and remember that the last file should be a directory.
>
> **Using the wildcard petter to copy multiple files (\*)**
>
> Instead of copying every filename you can just us the astrik to copy
> everything (\*)
>
> Example to copy all the text files
>
> cp \*.txt ~/project/backup/
>
> ** Handling Directories with -r**
>
> If you wish to copy a file without the -r, the directory would not be
> copy and instead linux will give you an error message. **because a
> directory is not a file** -- it’s a *container*, and copying it safely
> requires recursion.
>
> So to do so just
>
> cp favorite_song.mp3 music_folder/ ~/project/backup/ -r
>
>  
>
> **What is cp -t and why it exists**
>
> **Normal order**
>
>  
>
> cp file1 file2 destination/
>
> **With -t (destination FIRST)**
>
>  
>
> cp -t destination/ file1 file2
>
>  

- **Tip:** Use cp -i (interactive) if you want the system to ask for
  your permission before overwriting any of the multiple files.

> -- this will ask you if you want to overwrite it or nat use y/n to
> proceed
>
> **1. The Importance of the Trailing Slash /**
>
> When you typed ~/project/music/, the / at the end explicitly tells
> Linux: *"The destination is a directory."*
>
>  
>
>  
>
> **. Overwriting vs. Copying**
>
> Notice that after running cp, the original file favorite_song.mp3 is
> still in ~/project. This is the main difference
> between **cp (copy)** and **mv (move)**. Use cp when you want a
> duplicate, and mv when you want to relocate the original. It's like
> the differece between copy and cut
>
> Hohohohohoho hee I gerrit
>
>  
>
> **5. Seeing what's happening: The -v Option**
>
> If you want to see exactly what the command is doing, use
> the **verbose** flag:
>
> cp -v favorite_song.mp3 ~/project/music/
>
> It will output something like: 'favorite_song.mp3' -\>
> 'music/favorite_song.mp3'
>
> **1. If the destination is treated as a File name**
>
> If you run a command like:
>
> cp favorite_song.mp3 ~/project/new_folder
>
> If new_folder **does not exist**, Linux will:

- Create a **new file** named new_folder.

- Copy the contents of favorite_song.mp3 into it.

>  

*\#COPYING MULTIBLE FILES AT ONCE*

> You can copy multiple files in a single location. This is how to do so
>
> documents directory:
>
> cp ~/project/report1.txt ~/project/report2.txt ~/project/notes.txt
> ~/project/documents/ <span class="mark">Explain Code</span>
>
> This command copies report1.txt, report2.txt, and notes.txt to
> the documents directory. Here's how it works:

- cp: The copy command.

- ~/project/report1.txt ~/project/report2.txt ~/project/notes.txt: These
  are the source files we're copying. You can list as many files as you
  need, separated by spaces.

- ~/project/documents/: This is the destination directory.

>  
>
> The -i option stands for "interactive". It tells cp to ask for
> confirmation before overwriting any existing files. This is a safety
> measure to prevent accidental data loss.
>
>  
>
> Recursive Copying with the -r Option
>
> The -r option allows you to copy directories and their contents
> recursively. This is particularly useful for backing up entire
> directory structures.
>
> Let's create a backup of the entire website directory:
>
> cp -r ~/project/website ~/project/website_backup
> <span class="mark">Explain Code</span>
>
> This command copies the website directory and all its contents to a
> new directory called website_backup. Here's what each part means:

- cp: The copy command.

- -r: This option stands for "recursive". It tells cp to copy
  directories and their contents.

- ~/project/website: This is the source directory we're copying.

- ~/project/website_backup: This is the new directory where we're
  copying everything.

>  

* *

> **Preserving File Attributes with the -p Option**
>
> When copying files, you might want to preserve the original file's
> attributes such as timestamps and permissions. The -p option does this
> for you.
>
>  
>
> **Using Wildcards for Selective Copying**
>
> Wildcards allow you to copy multiple files based on patterns. This is
> useful when you want to copy files of a certain type or with specific
> naming conventions.
>
> Let's copy all text files to the text_files directory:
>
> cp ~/project/\*.txt ~/project/text_files/ <span class="mark">Explain
> Code</span>
>
> And copy all PDF files to the pdf_files directory:
>
> cp ~/project/\*.pdf ~/project/pdf_files/ <span class="mark">Explain
> Code</span>
>
> Here's what the wildcard (\*) means:

- \*.txt matches any file that ends with ".txt"

- \*.pdf matches any file that ends with ".pdf"

> This allows you to copy multiple files without listing them
> individually.
>
>  
>
> **Summary**
>
> I have learn

1.  Copy single files

2.  Copy files to different directories

3.  Copy multiple files at once

4.  Use the -i option for interactive copying

5.  Recursively copy directories with the -r option

6.  Preserve file attributes with the -p option

7.  Use wildcards for selective copying

> Additional cp options not covered in this lab include:

- -u: Copy only when the source file is newer than the destination file
  or when the destination file is missing

- -v: Verbose mode, explaining what is being done

- -n: No clobber; do not overwrite an existing file

- -l: Create hard links instead of copying files

- -s: Create symbolic links instead of copying files

> The cp command is a powerful tool for file management in Linux. With
> these skills, you're now equipped to handle a wide range of file
> copying tasks efficiently and effectively.
>
>  

*From
\<<https://labex.io/labs/linux-linux-cp-command-file-copying-209744?course=linux-basic-commands-practice-online>\>*
