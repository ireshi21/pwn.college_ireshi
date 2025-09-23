# Pondering Paths

## Challenge 1: The Root

### Solve
**Flag:** `pwn.college{ENIOhGQ74kp0CMG5iRosSHnX4sB.QX4cTO0wyMwAzNzEzW}`

```bash
hacker@pathsthe-root:$ /pwn
BOOM!!!
Here is your flag:
pwn.college{ENIOhGQ74kp0CMG5iRosSHnX4sB.QX4cTO0wyMwAzNzEzW}
```
### New Learnings

1. /root of the file system  

2. Absolute Path - independent of the current directory  
cat command- prints contents of the file in the terminal

3. Relative Path- Location relative to your current working directory  
does NOT start with /  
use . for current directory  
use .. for parent directory  
cd , ls

### References

ChatGPT to understand the theoretical part and info in the challenge description and slides.

# ----------------------------------------------------------------------------------------------------------

## Challenge 2: Program and absolute paths

### Solve
**Flag:** `pwn.college{oQTxyAjG0QPemh3vU4yNMYsDekz.QX1QTN0wyMwAzNzEzW}`


Absolute path

```bash
hacker@pathsprogram-and-absolute-paths:$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{oQTxyAjG0QPemh3vU4yNMYsDekz.QX1QTN0wyMwAzNzEzW}
```
### New Learnings

/root of the file system/ next file name 


### References

Info in the challenge description and slides.

# ----------------------------------------------------------------------------------------------------------
## Challenge 3: Position thy self

### Solve
**Flag:** `pwn.college{UDGWB_w9ydQ3n5ZZ9OkzXiX_evP.QX2QTN0wyMwAzNzEzW}`

1. Find out which directory it's located in  
2. Navigate to that directory  
3. Run challenge

```bash
hacker@paths~position-thy-self:~$ /challenge/run
Incorrect...
You are not currently in the /usr/share/doc directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:/$ cd /usr/share/doc
hacker@paths~position-thy-self:/usr/share/doc$ cd /challenge/run
bash: cd: /challenge/run: Not a directory
hacker@paths~position-thy-self:/usr/share/doc$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{UDGWB_w9ydQ3n5ZZ9OkzXiX_evP.QX2QTN0wyMwAzNzEzW}
hacker@paths~position-thy-self:/usr/share/doc$ 
```
### New Learnings

~: shows the current path that shell is located at  
cd: to change directory  
absolute path command: to navigate from the current directory  

challenge is a file, so cd is not applicable to it  


### References

Info in the challenge description and slides.

# ----------------------------------------------------------------------------------------------------------

## Challenge 4: Position Elsewhere

### Solve
**Flag:** `pwn.college{AQzihw9N3ppVMgr-3H3wfVKURmf.QX3QTN0wyMwAzNzEzW}`

1. Find out which directory it's located in  
2. Navigate to that directory  
3. Run challenge

```bash
hacker@paths~position-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /proc/148 directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:~$ cd /proc/148
hacker@paths~position-elsewhere:/proc/148$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{AQzihw9N3ppVMgr-3H3wfVKURmf.QX3QTN0wyMwAzNzEzW}
```
### New Learnings

 **If you put in absolute paths everywhere, then it really doesn't matter what directory you are in**


### References

Info in the challenge description and slides.

# ----------------------------------------------------------------------------------------------------------
## Challenge 5: Position yet elsewhere

### Solve
**Flag:** `pwn.college{oUDE6TYOuqQypUg283Vl1hy8nuo.QX4QTN0wyMwAzNzEzW}`

1. Find out which directory it's located in  
2. Navigate to that directory  
3. Run challenge

```bash
hacker@paths~position-yet-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /usr/share/zoneinfo/posix/Asia directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-yet-elsewhere:~$ cd /usr/share/zoneinfo/posix/Asia
hacker@paths~position-yet-elsewhere:/usr/share/zoneinfo/posix/Asia$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{oUDE6TYOuqQypUg283Vl1hy8nuo.QX4QTN0wyMwAzNzEzW}
```
### New Learnings

Same as previous challenge.


### References

Info in the challenge description and slides.


# ----------------------------------------------------------------------------------------------------------
## Challenge 6: implicit relative paths, from /

### Solve
**Flag:** `pwn.college{cAe2fDfSsN1KaVB5HBtJFQxU1G6.QX5QTN0wyMwAzNzEzW}`

1. Find out which directory it's located in (here , /)
2. Navigate to that directory  
3. Run challenge USING RELATIVE PATH WHICH MEANS DON'T USE "/"

```bash
hacker@paths~implicit-relative-paths-from-:~$ /challenge/run
Incorrect...
You are not currently in the / directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~implicit-relative-paths-from-:~$ challenge/run
bash: challenge/run: No such file or directory
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ /challenge/run
Incorrect...
You invoked this challenge with an absolute path. This challenge needs a relative path!
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{cAe2fDfSsN1KaVB5HBtJFQxU1G6.QX5QTN0wyMwAzNzEzW}
```
### New Learnings

1. Relative paths don't start with /  
2. Here, file is in "/" directory so path starts from ~~/~~ xyz 


### References

Info in the challenge description and slides.

# ----------------------------------------------------------------------------------------------------------
## Challenge 7: explicit relative paths, from /
### Solve
**Flag:** `pwn.college{I1rqcSmQ2Z0xDzSbhgwHXoQEEB4.QXwUTN0wyMwAzNzEzW}`

1. Find out which directory it's located in using absolute path
2. Navigate to that directory  
3. Run challenge

```bash

hacker@paths~explicit-relative-paths-from-:~$ /challenge/run
Incorrect...
You are not currently in the / directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{I1rqcSmQ2Z0xDzSbhgwHXoQEEB4.QXwUTN0wyMwAzNzEzW}
```
### New Learnings
 
. = the current directory  

.. = the parent directory  

./ = “look in the current directory” (explicitly)  

a trailing / or /. implies “this is a directory”  

### References

Used ChatGPT to understand relative path naming.

# ----------------------------------------------------------------------------------------------------------
## Challenge 8: implicit relative path
### Solve
**Flag:** `pwn.college{gLvoCB_wDen_mc13x53jBHWsYdL.QXxUTN0wyMwAzNzEzW}`


```bash
hacker@paths~implicit-relative-path:~$ cd /
hacker@paths~implicit-relative-path:/$ /challenge/run
Incorrect...
You are not currently in the /challenge directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~implicit-relative-path:/$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{gLvoCB_wDen_mc13x53jBHWsYdL.QXxUTN0wyMwAzNzEzW}
```
### New Learnings
 
Naked path = just the name of the file or directory (path that doesn’t have any ./ or ../ or slashes in front to tell the shell where to look explicitly)  

If you just provide a naked path to linux, it will throw an error  because programs with the same name as core system utilities could accidentally be executed. SO using ./ is important to convey that files ONLY IN THAT DIRECTORY need to be executed


### References

Challenge description and ChatGPT for better understanding.

# ----------------------------------------------------------------------------------------------------------
## Challenge 9: home sweet home
### Solve
**Flag:** `pwn.college{wL1G5vfcPA5HiBhKUEy2sXmc2II.QXzMDO0wyMwAzNzEzW}`

here, question specifies to create file in home directory, for which ~ is the shorthand. 


```bash
hacker@paths~home-sweet-home:~$ /challenge/run f
The argument you provided is not an absolute path!
hacker@paths~home-sweet-home:~$ /challenge/run ~f
The argument you provided is not an absolute path!
hacker@paths~home-sweet-home:~$ /challenge/run ~/f
Writing the file to /home/hacker/f!
... and reading it back to you:
pwn.college{wL1G5vfcPA5HiBhKUEy2sXmc2II.QXzMDO0wyMwAzNzEzW}
```
### New Learnings

SYNTAX for arguements:
program_name argument1 argument2 ...


### References

Challenge description and slides for syntax.



