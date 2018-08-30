# <span style="color:blue">Terminal and UNIX</style>
---
##Terminal Basics Exercises

####<span style="color:#6b6b6b">Part I</span>
__1. make a directory called first__

`mkdir first`

__2. change directory to the first folder__

`cd first`

__3. create a file called person.txt__

`touch person.txt`

__4. change the name of person.txt to another.txt__

`mv person.txt another.txt`

__5. make a copy of the another.txt file and call it copy.txt__

`cp another.txt copy.txt`

__6. remove the copy.txt file__

`rm copy.txt`

__7. make a copy of the first folder and call it second__

`cd ..`
`cp -r first second`

__8. delete the second folder__

`rm -r second`

####<span style="color:#6b6b6b">Part II</span>
__1. What does the `man` command do? Type in `man rm`. How do you scroll and get out?__

> `man` shows the manual page for a command. Scroll using the trackpad, mousewheel, or arrow keys.

__2. Look at the man page for ls. What does the -l flag do? What does the -a flag do?__

> `-l` lists directory contents in _long format_ and ouput a sum for all files sizes.  
> '-a' includes directories whose names begin with a dot (a.k.a *hidden* files and directories).

__3. Type the following command to download and save the contents of google.com: `curl https://www.google.com > google.html`__

`curl https://www.google.com > google.html`

__4. Use less to look at the contents of google.html.__

`less google.html`

__5. Look at the man page for less. Read the section on /pattern. Search for the text hplogo in the google.html file.__

`less -p hplogo google.html`

__6. How do you jump between words in the terminal?__

`Option + →` and `Option + ←`

__7. How do you get to the end of a line in terminal?__

> `Ctrl + E`

__8. How do you move your cursor to the beginning in terminal?__

> `Ctrl + A`

__9. How do you delete a word (without pressing backspace multiple times) in terminal?__

> `Ctrl + W`

__10. What is the difference between a terminal and shell?__

> A *terminal* is an environment or program that runs a shell. A *shell* is the command line interpreter.
 
__11. What is an absolute path?__

> An *absolute path* is relative to the root directory and always starts with `/`

__12. What is an relative path?__

> A *relative path* is relative to the current working directory.

__13. What is a flag? Give three examples of flags you have used.__

> Flags are a way to specify options for a command.  
> `-r` is the _recursive_ flag for a variety of commands to perform an operation on a directory and all of its contents recursively.  
> `-l` is the _long format_ flag and with `ls` lists directory contents in long format and outputs a sum for all files sizes.  
> `-a` is the _all_ flag for a variety of commands to include hidden files and directories.

__14. What do the r and f flags do with the rm command?__

>`-r` _recursive_ removes all contents of a directory recursively.  
>`-f` _force_ removes files regardless of permissions and without confirmation, or "forces" removal.

##Permissions, Redirection, and Piping Exercise

###<span style="color:#6b6b6b">Part I</span>
Write terminal commands to do the following:

__1. Create a file called restricted.txt.__  
`touch restricted.txt`

__2. Change the permissions on the restricted.txt file to allow the owner to read and write to the restricted.txt file. Do this using the Octal Notation.__  
`chmod 600 restricted.txt`

__3. Change the permissions on the restricted.txt file to only allow the owner, group and everyone to read and write and execute the restricted.txt file. Do this using the Symbolic notation.__  
`chmod ugo+rwx restricted.txt`

__4. Create a folder called secret\_files. Inside the secret\_files folder create a file called first_secret.txt and another folder called classified. Inside of the classified folder create a file called super_secret.txt.__  
`mkdir secret_files`  
`touch secret_files/first_secret.txt`  
`mkdir secret_files/classified`  
`touch secret_files/classified/super_secret.txt`

__5. Change the permissions on the secret\_files to only allow the owner and group to read, write and execute in all the files and folders inside of secret\_files. Do this using the Octal Notation.__  
`chmod -R 770 secret_files`

__6. Create a hard link for the restricted.txt called hard_link.__  
`ln restricted.txt hard_link`

__7. Create a symbolic link for the classified folder called classified_link.__  
`ln -s secret_files/classified classified_link`

### <span style="color:#6b6b6b">Part II</span>
For the following exercises, create a text file called `vegetables.txt` with the following text:

```
Lettuce  
Amaranth  
Beet  
Celery  
Kale  
Dill  
Cabbage  
Broccoli  
Lettuce  
Amaranth  
Beet  
Spinach  
Chard  
Broccoli  
Cabbage  
Dill
```


Write the following terminal commands to do the following

__1. Sort `vegetables.txt`.__  
`sort vegetables.txt`

__2. Count the number of lines in `vegetables.txt`.__  
`wc -l vegetables.txt`

__3. Create a file called `vegetables_sorted.txt` which contains all the unique vegetables sorted in ascending order in `vegetables.txt` (do this without the `touch` command).__  
`sort vegetables.txt | uniq > vegetables_sorted.txt`

__4. Create a file called `last_three.txt` which contains the last three vegetables in the `vegetables.txt` file (do this without the `touch` command).__  
`cat vegetables.txt | tail -n 3 > last_three.txt`

__5. Count the number of lines the word "Broccoli" appears on (using `wc` and `grep`).__  
`cat vegetables.txt | grep "Broccoli" | wc -l`

##Intermediate Terminal Exercises

###<span style="color:#6b66b">Part I</span>
Answer the following questions:

__1. Create an environment variable called FIRST\_NAME and set it equal to your first name (this does not need to be permanent).__  
`export FIRST_NAME=Kevin`

__2. Print the FIRST\_NAME variable.__  
`echo $FIRST_NAME`

__3. Print out the `$PATH` variable.__  
`echo $PATH`

__4. What is the `$PATH` variable?__  
> The `$PATH` variable is an environment variable that holds a list of the directory locations for executable programs.

__5. Why would you want to create an environment variable?__  
> To store useful data or path names that you can access using the variable.
__6. How do you permanently save environment variables?__  
> Append the appropriate `export VARNAME=value` line to the shell config file (.bashrc or .zshrc). 

__7. What is a process?__  
> A process is a program being run.

__8. How do you list all processes running on your machine?__  
`ps aux`

__9. What is a PID?__  
> A process ID number.

__10. How do you terminate a process?__  
> Using the `kill` command.

__11. What is the difference between kill and kill -9?__
> `kill -9` sends a different signal that kill in order to kill processes that are not responding to the normal kill signal.

__12. What grep flag allows for case insensitive search?__  
> `-i`

__13. What grep flag allows for a certain number of lines before the match?__  
> `-B`

__14. What grep flag allows for a certain number of lines around the match?__  
> `-C`

__15. What grep flag allows for a certain number of lines after the match?__  
> `-A`

__16. What grep flag allows for full word search?__  
> `-w`

__17. What grep flag shows you the line number of a match?__  
> `-n`

###<span style="color:#6b6b6b">Part II</span>

Write the following terminal commands to do the following (assume that `instructors.txt` is an imaginary file):

__1. Find all files inside the Desktop folder that have a name of "learn."__  
`find ~/Desktop -name "learn"`

__2. Find all files inside the Desktop folder that start with a "P."__  
`find ~/Desktop -name "P.*"`

__3. Find all files inside the Desktop folder that end with .txt.__  
`find ~/Desktop -name "*.txt"`

__4. Find all files inside the Desktop/views folder that have the name data somewhere in their filename.__  
`find ~/Desktop/views -name "*data*"`

__5. Inside of the instructors.txt file, output the number of times the word "Elie" appears.__  
`grep -c "Elie" instructors.txt`

__6. Inside of the instructors.txt file, list all matches for any full word that starts with a capital "P."__  
`grep -w "P.*" instructors.txt`

__7. Inside of the instructors.txt file, list all the line numbers for any full word that starts with a "z" (it should match regardless of upper or lower case).__  
`grep -ni "z.*" instructors.txt`


