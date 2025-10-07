# Chaining Commands

## Challenge 1: Changing File Ownership


### Solve

**Flag:** `pwn.college{0ps1aIIhcxedScLuTcCRGIajpDt.QX1UDO0wyMwAzNzEzW}`

```bash
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{0ps1aIIhcxedScLuTcCRGIajpDt.QX1UDO0wyMwAzNzEzW}
```
### New Learnings
The easiest way to chain commands is ;

; separates commands in a similar way to how Enter separates lines  





### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 2: Building on Success


### Solve

**Flag:** `pwn.college{04Zzcfa6_1jeKVlt9zHkfJO9fco.0lM0MDOxwyMwAzNzEzW}`

```bash
hacker@chaining~building-on-success:~$ /challenge/first-success && /challenge/second
Nice chaining! Flag: pwn.college{04Zzcfa6_1jeKVlt9zHkfJO9fco.0lM0MDOxwyMwAzNzEzW}
```
### New Learnings

The && operator allows you to run a second command only if the first command succeeds  
SYNTAX: hacker@dojo:~$ command1 && command2  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 3: Handling Failure

### Solve

**Flag:** `pwn.college{Ifjdmbi1IBonA4aEjgoPg0YgBDk.01M0MDOxwyMwAzNzEzW}`

```bash
hacker@chaining~handling-failure:~$ /challenge/first-failure || /challenge/second
Nice chaining! Flag: pwn.college{Ifjdmbi1IBonA4aEjgoPg0YgBDk.01M0MDOxwyMwAzNzEzW}
```
### New Learnings
the || operator allows you to run a second command only if the first command fails  
The || operator is super useful for providing fallback commands or error handling!  


### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 4: Your First Shell Script


### Solve

**Flag:** `pwn.college{kQoIux9x7sobhz1KbFl35VWvniX.QXxcDO0wyMwAzNzEzW}`
create a file x.sh and write /challenge/pwn;/challenge/college in it   
then go to terminal and execute-  
```bash
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{kQoIux9x7sobhz1KbFl35VWvniX.QXxcDO0wyMwAzNzEzW}
```
### New Learnings

you can write commands in a file with .sh extension  
then execute by bash filename.sh in terminal  

  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------


## Challenge 5: Redirecting Script Output (?)

### Solve

**Flag:** `pwn.college{woRAlfGiIkRSja0jFWUDoMQ-pvu.QXyEjN0wyMwAzNzEzW}`

```bash
hacker@practice~chaining~redirecting-script-output:~$ bash x.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{practice}
```
### New Learnings

same piping method

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 6: Executable Shell Scripts


### Solve

**Flag:** `pwn.college{Y18qMxn5YHNbqSPK757kFnSpsC2.QX0cjM1wyMwAzNzEzW}`

/challenge/solve written in x.sh in home directory  
change to executable file, so no need to use bash  

```bash
hacker@chaining~executable-shell-scripts:~$ chmod 555 x.sh
hacker@chaining~executable-shell-scripts:~$ /home/hacker/x.sh
Congratulations on your shell script execution! Your flag:
pwn.college{Y18qMxn5YHNbqSPK757kFnSpsC2.QX0cjM1wyMwAzNzEzW}
```
### New Learnings

if file is defined executable, no need to use bash  
  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------


## Challenge 7: Understanding Shebangs

### Solve

**Flag:** `pwn.college{s3HvuUpC_sacatqgzd6EUl1C7eX.0VOzMDOxwyMwAzNzEzW}`

```bash
hacker@chaining~understanding-shebangs:~$ chmod 555 ~/solve.sh
hacker@chaining~understanding-shebangs:~$ ~/solve.sh
hack the planet
hacker@chaining~understanding-shebangs:~$ /challenge/run
Testing your script...
Perfect! Your flag:
Flag: pwn.college{s3HvuUpC_sacatqgzd6EUl1C7eX.0VOzMDOxwyMwAzNzEzW}
```
### New Learnings

1. if the program file starts with the characters #! (often termed a "shebang"),  
2. shebang (#!) at the start of a file tells the system which interpreter should be used to run the script   

3. Commonly used-  
#!/bin/bash for bash scripts  
#!/usr/bin/python3 for Python scripts  
#!/bin/sh for POSIX shell scripts --- this is a more primitive predecessor to bash with fewer features, but more compatibility to non-Linux systems!  

#! = shebang  

/bin/bash = interpreter  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 8: Scripting with Arguements


### Solve

**Flag:** `pwn.college{wj8rlaX_l89L4kZuMySPFhOeE6y.0VNzMDOxwyMwAzNzEzW}`

File solve.sh contains:  
#!/bin/bash  
echo "$2 $1"  

```bash
hacker@chaining~scripting-with-arguments:~$ ~/solve.sh college_oV2L7t7ipQs pwn_fI9v8N7c8FM
pwn_fI9v8N7c8FM college_oV2L7t7ipQs
hacker@chaining~scripting-with-arguments:~$ /challenge/run
Correct! Your script properly reversed the arguments.
Here's your flag:
pwn.college{wj8rlaX_l89L4kZuMySPFhOeE6y.0VNzMDOxwyMwAzNzEzW}
```
### New Learnings

The script can access these arguments using special variables:  $n for nth arguement  

ex-hacker@dojo:~$ cat myscript.sh  
#!/bin/bash  
echo "First argument: $1"  
echo "Second argument: $2"  
hacker@dojo:~$ bash myscript.sh hello world  
First argument: hello  
Second argument: world  


### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 9: Scripting with Conditionals


### Solve

**Flag:** `pwn.college{45S2WCclCjl4gEweDbO-Nf-akVA.0lNzMDOxwyMwAzNzEzW}`  

Script contains:  
#!/bin/bash  
if [ "$1" = "pwn" ]  
then  
  echo "college"  
else  
  exit 0  
fi  


```bash
hacker@chaining~scripting-with-conditionals:~$ bash ~/solve.sh pwn
college
hacker@chaining~scripting-with-conditionals:~$ bash ~/solve.sh doodoo
hacker@chaining~scripting-with-conditionals:~$ /challenge/run
Correct! Your script properly handles all the conditions.
Here's your flag:
pwn.college{45S2WCclCjl4gEweDbO-Nf-akVA.0lNzMDOxwyMwAzNzEzW}
```
### New Learnings

if [ "$1" == "ping" ]  
then  
    echo "pong"  
fi  

RULES   
1. spaces before and after [ and ]  
2. indentation sensitive

add a 'then' before writing statement   


### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 10: Scripting with Default Cases


### Solve

**Flag:** `pwn.college{ARheuQqbwLjutVMSCAf5ORsQ9gt.01NzMDOxwyMwAzNzEzW}`

Script contains:  
#!/bin/bash  
if [ "$1" = "pwn" ]  
then  
  echo "college"  
else  
  echo "nope"  
fi  

```bash
hacker@chaining~scripting-with-default-cases:~$ bash ~/solve.sh pwn
college
hacker@chaining~scripting-with-default-cases:~$ /challenge/run
Correct! Your script properly handles the if/else conditions.
Here's your flag:
pwn.college{ARheuQqbwLjutVMSCAf5ORsQ9gt.01NzMDOxwyMwAzNzEzW}
hacker@chaining~scripting-with-default-cases:~$ bash ~/solve.sh doodoo
nope
```
### New Learnings

else handles all other cases not associated under if.  

  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 11: Scripting with Multiple Conditions


### Solve

**Flag:** `pwn.college{cs1rkektbn6O4fUq29dzn1QdL-Z.0FOzMDOxwyMwAzNzEzW}`

Solve.sh :  
if [ "$1" = "pwn" ]    
then    
  echo "college"   
elif [ "$1" = "hack" ]    
then    
  echo "the planet"    
elif [ "$1" = "learn" ]    
then     
  echo "linux"   
else  
  echo "unknown"  
fi 


```bash
hacker@chaining~scripting-with-multiple-conditions:~$ bash ~/solve.sh pwn
college
hacker@chaining~scripting-with-multiple-conditions:~$ bash ~/solve.sh learn
linux
hacker@chaining~scripting-with-multiple-conditions:~$ bash ~/solve.sh hack
the planet
hacker@chaining~scripting-with-multiple-conditions:~$ /challenge/run
Correct! Your script properly handles all the conditions with elif.
Here's your flag:
pwn.college{cs1rkektbn6O4fUq29dzn1QdL-Z.0FOzMDOxwyMwAzNzEzW}
```
### New Learnings

else if/ elif like in C
add a 'then' before writing statement  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 12: Reading Shell Scripts


### Solve

**Flag:** `pwn.college{o-TXI7ACmQanuxcKOswjmtMLuNd.0lMwgDOxwyMwAzNzEzW}`

```bash
hacker@chaining~reading-shell-scripts:~$ cat /challenge/run
#!/opt/pwn.college/bash

read GUESS
if [ "$GUESS" == "hack the PLANET" ]
then
        echo "CORRECT! Your flag:"
        cat /flag
else
        echo "Read the /challenge/run file to figure out the correct password!"
fi
hacker@chaining~reading-shell-scripts:~$ echo 'hack the PLANET' | /challenge/run
CORRECT! Your flag:
pwn.college{o-TXI7ACmQanuxcKOswjmtMLuNd.0lMwgDOxwyMwAzNzEzW}
```
### New Learnings
  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------
