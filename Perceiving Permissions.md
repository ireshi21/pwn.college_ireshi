# Perceiving Permissions

## Challenge 1: Changing File Ownership


### Solve

**Flag:** `pwn.college{cCSWNAfCgU952GSzMhDytqFCGTJ.QXxEjN0wyMwAzNzEzW}`
change ownership and read the flag

```bash
hacker@permissions~changing-file-ownership:~$ chown hacker /flag
hacker@permissions~changing-file-ownership:~$ cat /flag
pwn.college{cCSWNAfCgU952GSzMhDytqFCGTJ.QXxEjN0wyMwAzNzEzW}
```
### New Learnings

chown [username] [file]  

-requires you to be root to change in the first place  
 check out the permissions of a file or directory using ls -l  
  the d indicates that it's a directory, and the - represents that it's a normal file  



### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 2: Groups and Files


### Solve

**Flag:** `pwn.college{kIH-ZvsBQrqh6xXsSQcw94EPlbb.QXxcjM1wyMwAzNzEzW}`

```bash
hacker@permissions~groups-and-files:~$ cat /flag
cat: /flag: Permission denied
hacker@permissions~groups-and-files:~$ chgrp hacker /flag
hacker@permissions~groups-and-files:~$ cat /flag
pwn.college{kIH-ZvsBQrqh6xXsSQcw94EPlbb.QXxcjM1wyMwAzNzEzW}
```
### New Learnings

 Files have both an owning user and group. A group can have multiple users in it, and a user can be a member of multiple groups  
 
chgrp [OPTIONS] GROUP FILE...  
GROUP: the name (or GID) of the group you want the file to belong to.  

FILE... :  one or more files or directories whose group you want to change.  
  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 3: Fun with groups names

### Solve

**Flag:** `pwn.college{MFqIYblN6NvZikkBY9Dh1mdnh21.QXycjM1wyMwAzNzEzW}`

```bash
hacker@permissions~fun-with-groups-names:~$ id
uid=1000(hacker) gid=1000(grp15267) groups=1000(grp15267)
hacker@permissions~fun-with-groups-names:~$ chgrp grp15267 /flag
hacker@permissions~fun-with-groups-names:~$ cat /flag
pwn.college{MFqIYblN6NvZikkBY9Dh1mdnh21.QXycjM1wyMwAzNzEzW}
```
### New Learnings

1. id gives you info on user, pID and groups  

  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 4: Changing permissions 


### Solve

**Flag:** `pwn.college{MjAlBz2xVTAnN8yUzJZ6BtdgxAf.QXzcjM1wyMwAzNzEzW}`

```bash
hacker@permissions~changing-permissions:~$ chmod +r-- /flag
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{MjAlBz2xVTAnN8yUzJZ6BtdgxAf.QXzcjM1wyMwAzNzEzW}
```
### New Learnings

1. Each character of the three represent permission for a different type: 

r - user/group/other can read the file (or list the directory)  
w - user/group/other can modify the files (or create/delete files in the directory)  
x - user/group/other can execute the file as a program (or can enter the directory, e.g., using `cd`)  
- - nothing   

2. u=, g=, o=  
user, group, other user  

3. chmod [OPTIONS] MODE FILE  

4. OPTIONS can use numbers also- 4 for r  
2 for write  
1 for execution permission  

when writing for a specific 'user', use sum for whosever permission you want to grant  

5. WHO+/-WHAT, where WHO is user/group/other and WHAT is read/write/execute.  
EX- g+wx adds write and execute access to the group's permissions  
o-w removes write access for other users    


  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------


## Challenge 5: Executable Files

### Solve

**Flag:** `pwn.college{woRAlfGiIkRSja0jFWUDoMQ-pvu.QXyEjN0wyMwAzNzEzW}`

```bash
hacker@permissions~executable-files:~$ chmod u+rx /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
Successful execution! Here is your flag:
pwn.college{woRAlfGiIkRSja0jFWUDoMQ-pvu.QXyEjN0wyMwAzNzEzW}
```
### New Learnings

1. A file must have the execute bit set for your user to run it.  

2. ls -l shows permissions in the form -rwxr-xr-x  
3. If a file is owned by root:root and you’re an unprivileged user, you need the x bit in the others field to execute it.  


  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 6: Permission Tweaking Practice


### Solve

**Flag:** `pwn.college{gJc5d3ena8oBq4eHTs3aJjcStKx.QXwEjN0wyMwAzNzEzW}`

rw-r--r-- to ---r----- : chmod 000 /challenge/pwn  
---r----- to rwxrwx--- :  chmod u=rwx,g=rwx,o= /challenge/pwn  
rwxrwx--- to r--rwx--- : chmod 470 /challenge/pwn 


```bash
hacker@permissions~permission-tweaking-practice:~$ cat /flag
pwn.college{gJc5d3ena8oBq4eHTs3aJjcStKx.QXwEjN0wyMwAzNzEzW}
```
### New Learnings

4 - read (r)  
2 - write (w)  
1 - execute (x)

  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------


## Challenge 7: Permission setting practice

### Solve

**Flag:** `pwn.college{U94bmPDn2Zz5Se99t7SoUn_Hlmi.QXzETO0wyMwAzNzEzW}`

```bash
hacker@permissions~permissions-setting-practice:~$ chmod u=r,g=-,o=rx /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod 555 /flag
hacker@permissions~permissions-setting-practice:~$ cat /flag
pwn.college{U94bmPDn2Zz5Se99t7SoUn_Hlmi.QXzETO0wyMwAzNzEzW}
```
### New Learnings

(Practice)  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 8: The SUID Bit


### Solve

**Flag:** `pwn.college{sNyR8DKiVkvXm9oD5lzUBMp0S-B.QXzEjN0wyMwAzNzEzW}`

```bash
hacker@permissions~the-suid-bit:~$ chmod u+s /challenge/getroot
hacker@permissions~the-suid-bit:~$ cat flag
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "YJgJPjLr"
hacker@permissions~the-suid-bit:/$ /challenge/getroot
SUCCESS! You have set the suid bit on this program, and it is running as root! 
Here is your shell...
root@permissions~the-suid-bit:/# cat /flag
pwn.college{sNyR8DKiVkvXm9oD5lzUBMp0S-B.QXzEjN0wyMwAzNzEzW}
```
### New Learnings

1. SUID (Set User ID) makes a program run with the file owner’s privileges instead of the caller’s.  
2. On ls -l output, SUID shows as an s in the owner’s execute position (e.g., -rwsr-xr-x).  
3. If a root-owned binary has SUID, anyone who can execute it runs it as root while it runs.  
4. Set SUID as the file owner with SYNTAX: chmod u+s [program]  
5. SUID is commonly used for admin tools (like sudo, passwd) and for CTF challenges to allow controlled privilege escalation.  


  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------