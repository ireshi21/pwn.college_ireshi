# Digesting Documentation

## Challenge 1: learning-from-documentation

### Solve

They asked to pass /challenge/challenge as command and --giveflag as the arguement. 
**Flag:** `pwn.college{c6DOgilsQAx5YGlDbHJJieEIPVV.QX0ITO0wyMwAzNzEzW}`

```bash
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{c6DOgilsQAx5YGlDbHJJieEIPVV.QX0ITO0wyMwAzNzEzW}
```
### New Learnings

Syntax for command passing: [command] -[arguement]

### References

Challenge description and slides.

# ----------------------------------------------------------------------------------------------------------

## Challenge 2: learning-complex-usage

### Solve

Pass command -arguement -subarguement
**Flag:** `pwn.college{UMsOuiUHHjuZIWkH7wODiaOw2ZT.QX1ITO0wyMwAzNzEzW}`

```bash
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile
You must pass a file for --printfile to read!
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{UMsOuiUHHjuZIWkH7wODiaOw2ZT.QX1ITO0wyMwAzNzEzW}
```
### New Learnings

there are commands that take arguements to their arguements.  
Syntax for command passing: command -arguement -subarguement  

### References

Challenge description and slides.

# ----------------------------------------------------------------------------------------------------------

## Challenge 3: man~reading-manuals

### Solve
man to read manual for challenge
and execute 

**Flag:** `pwn.college{MayJrhGpvoOhWgoFhLanzsToTfk.QX0EDO0wyMwAzNzEzW}`

```bash
hacker@man~reading-manuals:~$ man challenge
hacker@man~reading-manuals:~$ 
hacker@man~reading-manuals:~$ challenge --ayrhpv 001
bash: challenge: command not found
hacker@man~reading-manuals:~$ /challenge/challenge --ayrhpv 001
Correct usage! Your flag: pwn.college{MayJrhGpvoOhWgoFhLanzsToTfk.QX0EDO0wyMwAzNzEzW}
```
### New Learnings

man = manual  
displays the manual of the command you pass as an arguement  
Syntax: man command  

after done reading, enter 'q' to quit  

SYNOPSIS: syntax type



### References

Challenge description and slides.

# ----------------------------------------------------------------------------------------------------------

## Challenge 4: man~searching-manuals

### Solve

in the manual for challenge, type /flag to search for the arguemnet which gives flag.

**Flag:** `pwn.college{IwUZ2ald5wK-FkTKyLvPyIs5WR9.QX1EDO0wyMwAzNzEzW}`

```bash
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge --mthtzgl
Initializing...
Correct usage! Your flag: pwn.college{IwUZ2ald5wK-FkTKyLvPyIs5WR9.QX1EDO0wyMwAzNzEzW}
```
### New Learnings

in manual, you can search using /[word]  
After searching, you can hit n to go to the next result and N to go to the previous result.   
Instead of /, you can use ? to search backwards!  



### References

Challenge description and slides.

# ----------------------------------------------------------------------------------------------------------

## Challenge 5: searching for manuals
### Solve

-didn't find anything by searching from /word in man man  
-man -k to search    
-gives manual cpvdhgwega  
-seaarch man cpvdhgwega  
-search for arg which gives flag (by /flag) in the manual  
-perform execution  

**Flag:** `pwn.college{cDMp23ISvYU0dh1gwI910ega6uL.QX2EDO0wyMwAzNzEzW}`

```bash
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man -k challenge
cpvdhgwega (1)       - print the flag!
hacker@man~searching-for-manuals:~$ apropos challenge
cpvdhgwega (1)       - print the flag!
hacker@man~searching-for-manuals:~$ man cpvdhgwega
hacker@man~searching-for-manuals:~$ challenge --cpvdhg 230
bash: challenge: command not found
hacker@man~searching-for-manuals:~$ /challenge/challenge --cpvdhg 230
Correct usage! Your flag: pwn.college{cDMp23ISvYU0dh1gwI910ega6uL.QX2EDO0wyMwAzNzEzW}
```
### New Learnings

full-text search of the manpage files can be done by (in terminal )  
1. man -K [name]  
OR apropos [name]  


### References

Challenge description and slides.

# ----------------------------------------------------------------------------------------------------------

## Challenge 6: Helpful Programs
### Solve

-didn't find anything by searching from /word in man man  
-man -k to search    
-gives manual cpvdhgwega  
-seaarch man cpvdhgwega  
-search for arg which gives flag (by /flag) in the manual  
-perform execution  

**Flag:** `pwn.college{cDMp23ISvYU0dh1gwI910ega6uL.QX2EDO0wyMwAzNzEzW}`

```bash
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man -k challenge
cpvdhgwega (1)       - print the flag!
hacker@man~searching-for-manuals:~$ apropos challenge
cpvdhgwega (1)       - print the flag!
hacker@man~searching-for-manuals:~$ man cpvdhgwega
hacker@man~searching-for-manuals:~$ challenge --cpvdhg 230
bash: challenge: command not found
hacker@man~searching-for-manuals:~$ /challenge/challenge --cpvdhg 230
Correct usage! Your flag: pwn.college{cDMp23ISvYU0dh1gwI910ega6uL.QX2EDO0wyMwAzNzEzW}
```
### New Learnings

Some programs don't have a man page, but might tell you how to run them if invoked with a special argument.  
 Usually, this argument is --help, but it can often be -h or, in rare cases,  
  -?, help, or other esoteric values like /?  
   (though that latter is more frequently encountered on Windows).


### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 7 : Help for builtins
### Solve


**Flag:** `pwn.college{IXuBSY5sneMxYMAXw8I4MTay5tX.QX0ETO0wyMwAzNzEzW}`

```bash
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    
    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "IXuBSY5s".
hacker@man~help-for-builtins:~$ challenge --secret IXuBSY5s
Correct! Here is your flag!
pwn.college{IXuBSY5sneMxYMAXw8I4MTay5tX.QX0ETO0wyMwAzNzEzW}
```
### New Learnings

Some commands are built into the shell itself. These are called builtins.   
You can get a list of shell builtins by running the builtin help, as so:

hacker@dojo:~$ help

You can get help on a specific one by passing it to the help builtin. hacker@dojo:~$ help cd  


### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------