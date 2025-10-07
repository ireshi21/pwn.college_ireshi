# Comprehending Commands

## Challenge 1: cat: not the pet, but the command!

### Solve
**Flag:** `pwn.college{4VLiRz7dPhg0-h5QtIDZOQ4MlbG.QXxcTN0wyMwAzNzEzW}`

```bash
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{4VLiRz7dPhg0-h5QtIDZOQ4MlbG.QXxcTN0wyMwAzNzEzW}
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag flag
pwn.college{4VLiRz7dPhg0-h5QtIDZOQ4MlbG.QXxcTN0wyMwAzNzEzW}
pwn.college{4VLiRz7dPhg0-h5QtIDZOQ4MlbG.QXxcTN0wyMwAzNzEzW}
```
### New Learnings

1. `cat` is most often used for reading out files  
2. cat will concatenate (hence the name) multiple files if provided multiple arguments  
3.  if you give no arguments at all, cat will read from the terminal input and output it



### References

Challenge description and geekforgeeks.

# ----------------------------------------------------------------------------------------------------------

## Challenge 2: catting absolute paths

### Solve
**Flag:** `pwn.college{gJw0r3pc64QEVE0VHUjImMmb8UO.QX5ETO0wyMwAzNzEzW}`

```bash
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{gJw0r3pc64QEVE0VHUjImMmb8UO.QX5ETO0wyMwAzNzEzW}
```
### New Learnings

1.  cat's arguments can be described as absolute paths  

eg: hacker@dojo:~$ cat /challenge/DESCRIPTION.md  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 3: more-catting-practice

### Solve
**Flag:** `pwn.college{QxoeOWH64EX-R4uEC-NzHXggV0D.QXwITO0wyMwAzNzEzW}`

```bash
hacker@commands~more-catting-practice:~$ cat /usr/lib/ipxe/flag
pwn.college{QxoeOWH64EX-R4uEC-NzHXggV0D.QXwITO0wyMwAzNzEzW}
```
### New Learnings

1.  cat can read a file directly by specifying it's absolute path

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 4: grepping-for-a-needle-in-a-haystack

### Solve
**Flag:** `pwn.college{UtRCBjrCNE1bzuZsIFNWd1GMO1n.QX3EDO0wyMwAzNzEzW}`

```bash
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep -n  pwn.college /challenge/data.txt
72378:pwn.college{UtRCBjrCNE1bzuZsIFNWd1GMO1n.QX3EDO0wyMwAzNzEzW}
```
### New Learnings

1.  GREP  
hacker@dojo:~$ grep SEARCH_STRING /path/to/file  
-i or --ignore-case: Ignores case distinctions when matching the pattern.  
-v or --invert-match: Selects lines that do not match the pattern.  
-n or --line-number: Prints the line number along with the matching line.  
-c or --count: Prints only a count of the matching lines, not the lines themselves.  
-l or --files-with-matches: Prints only the names of files containing matches, not the matching lines.  
-r or --recursive: Searches recursively through directories.  

### References

Challenge description and geekforgeeks.

# ----------------------------------------------------------------------------------------------------------

## Challenge 5: comparing files

### Solve
**Flag:** `pwn.college{Yx_VhhfWk2ovuo-_s__-MM04GK6.01MwMDOxwyMwAzNzEzW}`

```bash
hacker@commands~comparing-files:~$ cd /challenge
hacker@commands~comparing-files:/challenge$ diff decoys_only.txt decoys_and_real.txt
60a61
> pwn.college{Yx_VhhfWk2ovuo-_s__-MM04GK6.01MwMDOxwyMwAzNzEzW}
```
### New Learnings

1. diff compares two files line by line and shows you exactly what's different between them.  
1a2 means "after line 1 of file1, add line 2 of file2"  
line 2 changed (2c2) 


### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 6: listing files

### Solve
**Flag:** `pwn.college{IRU7u6vWgSIYywZSEj0HYNmYcNX.QX4IDO0wyMwAzNzEzW}`

```bash
hacker@commands~listing-files:/challenge$ ls /challenge
18701-renamed-run-3303  DESCRIPTION.md
hacker@commands~listing-files:/challenge$ cat 18701-renamed-run-3303
#!/opt/pwn.college/bash
echo "Yahaha, you found me! Here is your flag:"
cat /flag
hacker@commands~listing-files:/challenge$ /challenge/18701-renamed-run-3303 ~/flag
Yahaha, you found me! Here is your flag:
pwn.college{IRU7u6vWgSIYywZSEj0HYNmYcNX.QX4IDO0wyMwAzNzEzW}
```
### New Learnings

1. ls will list files in all the directories provided to it as arguments, and in the current directory if no arguments are provided  
2. cat reads contents of the file, absolute path runs the file which has instructions for the computer  (for ex, running flag)
3. /challenge/18701-renamed-run-3303 ~/flag explained
 
/challenge/18701-renamed-run-3303  

The program/executable you are running.  

Absolute path ensures Linux knows exactly where it is.  

Has permission to read the protected /flag file.  
  
~/flag : argument to the program  

~ expands to your home directory (/home/hacker).  

Instructs the program where to write the flag.  
 
What happens when you run it:  

The program reads /flag (hidden/protected).  

Writes its contents to /home/hacker/flag. 

OR
because the /challenge/run is renamed to /challenge/18701-renamed-run-3303, only execution of that command alone will be sufficient.


### References


Challenge description and GPT to clear doubts.


# ----------------------------------------------------------------------------------------------------------

## Challenge 7: touching files

### Solve
**Flag:** `pwn.college{0Vl1U8xx83HSolOGsURQgz9Wymn.QXwMDO0wyMwAzNzEzW}`

```bash
hacker@commands~touching-files:~$ cd /tmp
hacker@commands~touching-files:/tmp$ touch /pwn
touch: cannot touch '/pwn': Permission denied
hacker@commands~touching-files:/tmp$ touch pwn
hacker@commands~touching-files:/tmp$ touch college
hacker@commands~touching-files:/tmp$ /challenge/run
Success! Here is your flag:
pwn.college{0Vl1U8xx83HSolOGsURQgz9Wymn.QXwMDO0wyMwAzNzEzW}
```
### New Learnings

files are created using 'touch filename' command.
 
### References


Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 8: removing files

### Solve
**Flag:** `pwn.college{kmavJbgiIyt9diBxPVTkzn1shx9.QX2kDM1wyMwAzNzEzW}`

```bash
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ ls
f
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{kmavJbgiIyt9diBxPVTkzn1shx9.QX2kDM1wyMwAzNzEzW}
```
### New Learnings

In Linux, you remove files with the rm command  
 
### References


Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 9: moving files

### Solve
**Flag:** `pwn.college{MQw5FdIP_A_BM1UWiMkF4_OqTdK.0VOxEzNxwyMwAzNzEzW}`

```bash
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{MQw5FdIP_A_BM1UWiMkF4_OqTdK.0VOxEzNxwyMwAzNzEzW}
```
### New Learnings

move files around with the mv command  
syntax: mv old_filename new_filename  
 
### References
Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 10: hidden files

### Solve
**Flag:** `pwn.college{gMDhSgL6KXvIycRFCRxqcLgS5yf.QXwUDO0wyMwAzNzEzW}`

Q- Go find the flag, hidden as a dot-prepended file in /.

```bash
hacker@commands~hidden-files:~$ cd /
hacker@commands~hidden-files:/$ ls -a
.   .dockerenv            bin   challenge  etc   lib    lib64   media  nix  proc  run   srv  tmp  var
..  .flag-54101044112990  boot  dev        home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~hidden-files:/$ cat .flag*
pwn.college{gMDhSgL6KXvIycRFCRxqcLgS5yf.QXwUDO0wyMwAzNzEzW}
```
### New Learnings

ls doesn't list all the files by default.   
Linux has a convention where files that start with a "." don't show up by default in ls and in a few other contexts.  
To view them with ls, you need to invoke ls with the -a flag, i.e, ls -a
 
### References
Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 11: An Epic Filesystem Quest

### Solve
**Flag:** `pwn.college{UbZkm7v7CnZ2TOqtepc8eB7Xt-a.QX5IDO0wyMwAzNzEzW}`  

Challenge involves using different way to access and read files.   
1. to read without going into the directory, i.e., without using cd, you use- cat /absolute path  
2. to read files which start with ".", ls -a /path is used


### New Learnings

1. if you're already in a path, for example  
user/office$
then to further go into a directory, use ./ (it traverses after office)
if /name is used, then it's absolute path which starts from the home directory.
 
### References
Previous markdown notes.

# ----------------------------------------------------------------------------------------------------------

## Challenge 12: making directories
### Solve
**Flag:** `pwn.college{omEFMlgeshdarNwlbt_TuPaewH7.QXxMDO0wyMwAzNzEzW}`

```bash
hacker@commands~making-directories:~$ cd /tmp
hacker@commands~making-directories:/tmp$ mkdir pwn
hacker@commands~making-directories:/tmp$ cd pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{omEFMlgeshdarNwlbt_TuPaewH7.QXxMDO0wyMwAzNzEzW}

```
### New Learnings

We can create files using touch  
You make directories using the mkdir command  
### References
Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 13: finding files
### Solve
**Flag:** `pwn.college{cpRAxVeuvWamdrEOmFC60qu7Td7.QXyMDO0wyMwAzNzEzW}`

```bash
hacker@commands~finding-files:~$ ~
bash: /home/hacker: Is a directory
hacker@commands~finding-files:~$ find / -name flag
find: ‘/root’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/tmp/tmp.TpSOPGOVKK’: Permission denied
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
/usr/share/racket/pkgs/scribble-lib/scribble/lncs/compiled/flag
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
/nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
/nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag
/nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/h88mxp2mbgyj06vypwmqpy05idhwimnp-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/5qz6hgb1qzpvjrsw20wyiylx5zw8b9bk-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
hacker@commands~finding-files:~$ ls -a^C
hacker@commands~finding-files:~$ ls -a /usr/local/lib/python3.8/dist-packages/pwnlib/flag
.  ..  __init__.py  __pycache__  flag.py
hacker@commands~finding-files:~$ ls -a /usr/share/racket/pkgs/scribble-lib/scribble/lncs/compiled/flag
/usr/share/racket/pkgs/scribble-lib/scribble/lncs/compiled/flag
hacker@commands~finding-files:~$ cat /usr/share/racket/pkgs/scribble-lib/scribble/lncs/compiled/flag
pwn.college{cpRAxVeuvWamdrEOmFC60qu7Td7.QXyMDO0wyMwAzNzEzW}hacker@commands~finding-files:~$ 

```
### New Learnings

The "find" command in Linux is a powerful command-line utility used to search for files and directories within a specified directory   hierarchy. It allows you to locate files based on various criteria, including:   
  Name: Search for files or directories by their exact name or a pattern using wildcards.  
  Type: Specify whether to search for regular files (-type f), directories (-type d), symbolic links (-type l), etc.  
  Size: Find files based on their size (e.g., greater than, less than, or exactly a certain size).  
  Time: Locate files based on their modification time (-mtime), access time (-atime), or change time (-ctime).  
  Permissions: Search for files with specific permissions.  
  Owner/Group: Find files belonging to a particular user or group.  
find [path] [expression]  

Example — Find a file named filename.txt in the current directory  
Syntax — find . -name "filename.txt"  

Example — Find all files ending with .log in /var/log  
Syntax — find /var/log -name "*.log"  

Example — Find all directories in your home directory  
Syntax — find ~ -type d  

Example — Find files larger than 10 MB starting at root (/)  
Syntax — find / -size +10M  

Example — Find files modified in the last 7 days in a given path  
Syntax — find /path/to/search -mtime -7  


### References
Challenge description, geekforgeeks.

# ----------------------------------------------------------------------------------------------------------

## Challenge 14: linking files
### Solve
**Flag:** `pwn.college{Y48bA9Lx0nIKh3obHTnBD8DdcWR.QX5ETN1wyMwAzNzEzW}`

```bash
hacker@commands~linking-files:~$ ln -s /flag ~/not-the-flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{Y48bA9Lx0nIKh3obHTnBD8DdcWR.QX5ETN1wyMwAzNzEzW}

```
### New Learnings
Links in UNIX  

1. A link is like a pointer or shortcut to a file/directory.  

2. Two types: Hard links and Soft (symbolic) links.  

3. Difference:  

Hard links point directly to the same data (inode).    

Soft links point to the file path. If the file is moved/deleted, they break.  

4. Hard Links   

Share the same inode as the original file.  

Survive renaming or deleting of the original file (until all links are removed).  

Cannot be created across different filesystems.  

Cannot be created for directories.  

ls -l shows the number of hard links.  

Content and size are identical in all hard links.  

Removing one link only reduces the count, doesn’t delete data.  

Command:  
ln original_file link_name  

5. Soft (Symbolic) Links  

Like a Windows shortcut.  

Have a different inode; store the path of the target file.  

Can be used across filesystems.  

Can be created for directories.  

ls -l shows with an l at the start and displays link -> target.  

Size of link = length of target file path.  

If the target file is renamed, moved, or deleted → link breaks (dangling).  

Removing a symlink does not affect the original file.  

Command:  
ln -s original_file link_name   
### References
Challenge description, slides and geekforgeeks.









