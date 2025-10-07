# Pondering PATH

## Challenge 1: Launching Screen


### Solve

**Flag:** `pwn.college{oLWa2s5qf_fJX1VQ_KsRVhj6U0Y.0VN4IDOxwyMwAzNzEzW}`
change ownership and read the flag

```bash
hacker@path~the-path-variable:~$ PATH=""
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{UnxCgTcOt1WuI6UAHyiokQsl_Eq.QX2cDM1wyMwAzNzEzW}
```
### New Learnings

1. PATH is an environmental variable in Linux and other Unix-like operating systems that tells the shell which directories to search for executable files (i.e., ready-to-run programs) in response to commands issued by a user. 
2.  PATH, that stores a bunch of directory paths in which the shell will search for programs corresponding to commands.  
3. Without a PATH, bash cannot find the ls command.  
4. PATH is just a colon-separated list of directories, e.g.  
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin  
5. export PATH= or PATH= makes it empty.  

Consequence: commands typed by name (e.g. ls, grep, ssh, bash) will usually fail with command not found.  
6. Shell builtins (like cd, echo, read, printf) still work because they are built into the shell.  
7. export PATH=/usr/bin:/bin to restore  




### References

Challenge description and CHATGpt for theory.

# ----------------------------------------------------------------------------------------------------------

## Challenge 2: Setting Path 


### Solve

**Flag:** `pwn.college{AA7hzEpVPd_WKHGPq-sRHV8F-gp.QX1cjM1wyMwAzNzEzW}`



```bash
hacker@path~setting-path:~$ PATH=/challenge/more_commands/
hacker@path~setting-path:~$ /challenge/run win
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{AA7hzEpVPd_WKHGPq-sRHV8F-gp.QX1cjM1wyMwAzNzEzW}
```
### New Learnings

1. If you specify a script's path in PATH variable, you can execute it directly.
e.g.: hacker@dojo:~$ PATH=/home/hacker/scripts  
hacker@dojo:~$ goodscript  
YEAH! This is the best script!  

 
### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 3: Finding Commands

### Solve

**Flag:** `pwn.college{0znK8v-LvQycJPfcnPMYs-9N1yc.01NzEzNxwyMwAzNzEzW}`

```bash
hacker@path~finding-commands:~$ which win
/challenge/paths/11996/win
hacker@path~finding-commands:~$ cat /challenge/paths/11996/flag
pwn.college{0znK8v-LvQycJPfcnPMYs-9N1yc.01NzEzNxwyMwAzNzEzW}
```
### New Learnings

1. Mirroring what the shell does when searching for commands, which looks at each directory in $PATH in order and prints the first file it finds whose name matches the argument you passed.  
2. which [command] will give you the path of where it's stored in the respective directory  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 4: Adding Commands


### Solve

**Flag:** `pwn.college{IfAlnJzX3pGZuVWKZY9WKQZVSKZ.QX2cjM1wyMwAzNzEzW}`

In file-  win  
#!/bin/bash
read -r FLAG </flag
printf '%s' "$FLAG"

```bash
hacker@path~adding-commands:~$ mkdir -p /home/hacker/bin
hacker@path~adding-commands:~$ chmod +x /home/hacker/bin/win
hacker@path~adding-commands:~$ PATH=/home/hacker/bin /challenge/run
Invoking 'win'....
pwn.college{IfAlnJzX3pGZuVWKZY9WKQZVSKZ.QX2cjM1wyMwAzNzEzW}
```
### New Learnings

execute using shell script  
if you overwrite PATH, all other paths get erased  
so use inbuilt commands or update, not overwrite PATH  

  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------


## Challenge 5: Hijacking Commands

### Solve

**Flag:** `pwn.college{kVdTfJkk8Y5NY5t8H7FaBtWwONP.QX3cjM1wyMwAzNzEzW}`

Idea: create another fake rm command script and set it as priority in PATH variable so /challenge/run stumbles upon that first
In Flag-  
#!/bin/bash  
cat /flag   

```bash
hacker@path-hijacking-commands:~$ chmod +x ~/bin/rm
hacker@path-hijacking-commands:~$ PATH=~/bin:$PATH
hacker@path-hijacking-commands:~$ /challenge/run
Trying to remove /flag...
Found 'rm' command at /home/hacker/bin/rm. Executing!
pwn.college{kVdTfJkk8Y5NY5t8H7FaBtWwONP.QX3cjM1wyMwAzNzEzW}
```
### New Learnings

You can create commands and set them as priority in the terminal.  
### References

Challenge description and chatgpt on how to set it as priority.


