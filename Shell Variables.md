# Shell Variables

## Challenge 1: Printing Variables


### Solve

**Flag:** `pwn.college{Q2DkZfrPFUYlUSaj_YEM-7dQFGZ.QX3UTN0wyMwAzNzEzW}  `

```bash
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{Q2DkZfrPFUYlUSaj_YEM-7dQFGZ.QX3UTN0wyMwAzNzEzW}
```
### New Learnings

variables store some value which can printed using echo $variable  
'$'- used to access variables  
In shell terms, this prepending of $ triggers what is called variable expansion, and is, surprisingly, the source of many potential vulnerabilities 
  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 2: Setting Variables


### Solve

**Flag:** `pwn.college{MznKIbPYwJuXKqQoxspWfgFOzQ9.QX5UTN0wyMwAzNzEzW}  `

```bash
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{MznKIbPYwJuXKqQoxspWfgFOzQ9.QX5UTN0wyMwAzNzEzW}
```
### New Learnings
write values to variables. This is done, as with many other languages, using =  
(no spaces around the =)   

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 3: Multi-word Variables


### Solve

**Flag:** `pwn.college{UzE8fNDziAYy71U0eABQZ_Ifq2_.QXwYTN0wyMwAzNzEzW}`

```bash
hacker@variables~multi-word-variables:~$ PWN='COLLEGE YEAH'
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{UzE8fNDziAYy71U0eABQZ_Ifq2_.QXwYTN0wyMwAzNzEzW}
```
### New Learnings
hacker@dojo:~$ VAR="1337 SAUCE" and not VAR= 1337 SAUCE (shell will think as arguement) 

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 4: Exporting Variables


### Solve

**Flag:** `pwn.college{oPvh9Kc37vxX5yTtbRLjyipT-ea.QXyYTN0wyMwAzNzEzW}`

```bash
hacker@variables~exporting-variables:~$ export PWN=COLLEGE
hacker@variables~exporting-variables:~$ COLLEGE=PWN
hacker@variables~exporting-variables:~$ /challenge/run 
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great 
job! Here is your flag:
pwn.college{oPvh9Kc37vxX5yTtbRLjyipT-ea.QXyYTN0wyMwAzNzEzW}
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
```
### New Learnings
By default, variables that you set in a shell session are local to that shell process. That is, other commands you run won't inherit them.  
to do so- use export  
hacker@dojo:~$ export VAR=1337  
 When you export your variables, they are passed into the environment variables of child processes.  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 5: Printing Exporting Variables


### Solve

**Flag:** `pwn.college{4ybG6NAUGRxia8LdMskruK7W1pI.QX4UTN0wyMwAzNzEzW}`

```bash
hacker@variables~printing-exported-variables:~$ env
SHELL=/run/dojo/bin/bash
HOSTNAME=variables~printing-exported-variables
PWD=/home/hacker
MANPATH=/run/dojo/share/man:
DOJO_AUTH_TOKEN=03ebc6eaf44b54ea684fbce016fabcb666b95d0282c6cfd24910f8a1d19692d9
HOME=/home/hacker
LANG=C.UTF-8
FLAG=pwn.college{4ybG6NAUGRxia8LdMskruK7W1pI.QX4UTN0wyMwAzNzEzW}
TERMINFO=/run/dojo/share/terminfo
TERM=xterm-256color
SHLVL=2
LC_CTYPE=C.UTF-8
SSL_CERT_FILE=/run/dojo/etc/ssl/certs/ca-bundle.crt
PATH=/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
DEBIAN_FRONTEND=noninteractive
_=/run/dojo/bin/env
```
### New Learnings
 env command: it'll print out every exported variable set in your shell  
 echo command is also used to print variables  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 6: Storing command output


### Solve

**Flag:** `pwn.college{U7YFerYj6XWrYx804pjFpnxeVDu.QX1cDN1wyMwAzNzEzW}`

```bash
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out 
and submit it!
hacker@variables~storing-command-output:~$ echo $PWN
pwn.college{U7YFerYj6XWrYx804pjFpnxeVDu.QX1cDN1wyMwAzNzEzW}
```
### New Learnings
 to store the output of some command into a variable  
 hacker@dojo:~$ FLAG=$(cat /flag)  
hacker@dojo:~$ echo "$FLAG"  
pwn.college{blahblahblah}  
 here- runs cat /flag - stores output in FLAG  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------


## Challenge 8: Reading Files


### Solve

**Flag:** `pwn.college{UqnDsUwsMiYP_q96IBBKdFXmAAz.QXwIDO0wyMwAzNzEzW}`

```bash
hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{UqnDsUwsMiYP_q96IBBKdFXmAAz.QXwIDO0wyMwAzNzEzW}
```
### New Learnings
read [variablename] < [filename/path]

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------