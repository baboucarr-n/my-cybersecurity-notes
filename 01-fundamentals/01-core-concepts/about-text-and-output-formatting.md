Text-Fu Again

04 April 2026

19:19

 

**Standard Input and Standard output**

 

I can see how commands produce output to our screen terminal, now withh
this comes to this important concept in linux called I/O streams.

<table style="width:100%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 86%" />
</colgroup>
<thead>
<tr>
<th>NOTE- CONCEPT:</th>
<th><table style="width:84%;">
<colgroup>
<col style="width: 84%" />
</colgroup>
<thead>
<tr>
<th>Under normal circumstances every Linux program has three streams
opened when it starts; one for input; one for output; and one for
printing diagnostic or error messages. These are typically attached to
the user's terminal (see man tty(4)) but might instead refer to files or
other devices, depending on what the parent process chose to set
up.</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align: right;">--Taken from the BSD Library functions
manual - STDIN(3)</td>
</tr>
</tbody>
</table>
<p> </p>
<p><em>From &lt;<a
href="https://www.learnlinux.org.za/courses/build/shell-scripting/ch01s04#:~:text=Linux%20is%20built%20being%20able,same%20as:%20cat%20myfirstscript).">https://www.learnlinux.org.za/courses/build/shell-scripting/ch01s04#:~:text=Linux%20is%20built%20being%20able,same%20as:%20cat%20myfirstscript).</a>&gt;</em></p>
<p> </p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

 

 

 

BUT FIRST BATIST LETS UNDERSTAND THIS WELL:

 

THIS CONCEPT IN LINUX CALLED EVERYTHING IN LINUX IS A FILE:

When we say everything in linux is a file this include even the screen,
the keyboard everything is a file in the linux system! These are called
"strems" So when we start our linux machine all these files run forming
a complete machine. So for standard input what ever we type into our
terminal these is load into the standard input -- taking the copmmand
and allowing the shell to execute it

 

---

 

SUMMARY CORRECTION: You correctly identified that everything in Linux is
a file including keyboard and screen, and that stdin carries typed
commands to programs. However, these files don't "run"—they're static
interfaces that programs open as file descriptors (0, 1, 2) at startup.
It's "streams" not "strems," and "this is loaded" not "these is load."
Most importantly, stdin doesn't only come from keyboard—it can also come
from files via redirection (\`\<\`) or from other programs via pipes
(\`\|\`).

 

---

 

 

Understanding stdin and stdout

Every command-line process in Linux operates with at least two
fundamental data streams: standard input (stdin) and standard output
(stdout). A program reads data from stdin and writes its results
to stdout.

 

*From \<<https://labex.io/lesson/stdin-standard-in-redirect>\>*

 

 

 

 

STDIN(standard Input): by default when you entering a command your are
entering it into standard input terminal

 

| CommandExample: | echo HelloWord \> newfile.txt |
|-----------------|-------------------------------|

 

Here echo is using the standard output to display the text into a file
called newFile.txt

---

 

\*\*SUMMARY CORRECTION:\*\* Almost perfect! Just one fix: \`\>\` doesn't
"display" into the file—it \*\*redirects and saves\*\* into the file.
Displaying happens on screen (terminal). When you use \`\>\`, stdout
never reaches your eyes; it gets captured by the file instead. So: echo
creates output → \`\>\` hijacks stdout → file stores it. No display, no
stdin involved.

 

---

 

REDIRECTING STDOUT

 

> **We use the \> sign to redirect standard output into a file or other
> destination.**
>
> **But whenever we use the \> command it will override whatever is in
> the destination file, therefore removing the content in that
> particular file**
>
>  
>
>  
>
> **To solve this use the append instead which is \>\> This will just
> add whatever we want to add into the file while leaving the original
> content intact**
>
>  
>
>  
>
>  
>
> **Two exmaples:**
>
>  

<table style="width:69%;">
<colgroup>
<col style="width: 10%" />
<col style="width: 57%" />
</colgroup>
<thead>
<tr>
<th><strong>Ex1:</strong></th>
<th><p><strong>echo helloWOrd &gt; newFile.txt</strong></p>
<p> </p>
<p><strong>Here we are overwriting the content in the original
file</strong></p></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Ex2</strong></td>
<td><p><strong>echo helloWorld &gt;&gt; newFile.txt</strong></p>
<p> </p>
<p><strong>Here we are appending the text into the
file</strong></p></td>
</tr>
<tr>
<td> </td>
<td> </td>
</tr>
</tbody>
</table>

>  

<table style="width:76%;">
<colgroup>
<col style="width: 10%" />
<col style="width: 65%" />
</colgroup>
<thead>
<tr>
<th><strong>NOTE:</strong></th>
<th><p>A program reads data from stdin and writes its results
to stdout.</p>
<p> </p>
<p><em>From &lt;<a
href="https://labex.io/lesson/stdin-standard-in-redirect">https://labex.io/lesson/stdin-standard-in-redirect</a>&gt;</em></p>
<p> </p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

>  

REDIRECTING STDIN :

 
