# Practicing Piping

## Challenge 1: Redirecting Output


### Solve

**Flag:** `pwn.college{URRRlStY8t0tsG6lYcOsp6_tP0L.QX0YTN0wyMwAzNzEzW}`

```bash
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your 
flag:
pwn.college{URRRlStY8t0tsG6lYcOsp6_tP0L.QX0YTN0wyMwAzNzEzW}
```
### New Learnings

redirecting stdout to files. You can accomplish this with the > character  
command content > filename   
ex: echo hi > file 

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 2: Redirecting more Output


### Solve

**Flag:** `pwn.college{IbG3SIRpRyRkMV6NM0thq9EGSD9.QX1YTN0wyMwAzNzEzW}`

```bash
hacker@piping~redirecting-more-output:~$ /challenge/run
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[FAIL] You did not satisfy all the execution requirements.
[FAIL] Specifically, you must fix the following issue:
[FAIL]   You have not redirected anything for this process stdout.
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{IbG3SIRpRyRkMV6NM0thq9EGSD9.QX1YTN0wyMwAzNzEzW}
```
### New Learnings

redirecting stdout to files. You can accomplish this with the > character  
command content > filename   
ex: echo hi > file 

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 3: Appending Output


### Solve

**Flag:** `pwn.college{IrCVJKzu6ixm5JHSpA3WwcL7_T-.QX3ATO0wyMwAzNzEzW}`

```bash
:
 v 
pwn.college{IrCVJKzu6ixm5JHSpA3WwcL7_T-.QX3ATO0wyMwAzNzEzW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>) 
rather than *append* mode (>>), and so the write of the second half to stdout 
overwrote the initial write of the first half directly to the file. Try append 
```
### New Learnings

> is used to write in a file  
if it's used again for the same file, it will overwrite the content  
to append, use command content >> filename  


### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 4: Redirecting Errors


### Solve

**Flag:** `pwn.college{gg6goD91DaUP4rg6i92oc3MTAfn.QX3YTN0wyMwAzNzEzW}`

```bash
hacker@piping~redirecting-errors:~$ /challenge/run 1>myflag 2>instructions
hacker@piping~redirecting-errors:~$ cd instructions
bash: cd: instructions: Not a directory
hacker@piping~redirecting-errors:~$ cat instructions
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will check that error output is redirected to a specific file path : instructions
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!

[TEST] You should have redirected my stderr to instructions. Checking...

[PASS] The file at the other end of my stderr looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-errors:~$ instructions/feedback
bash: instructions/feedback: Not a directory
hacker@piping~redirecting-errors:~$ cat instructions/feedback
cat: instructions/feedback: Not a directory
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{gg6goD91DaUP4rg6i92oc3MTAfn.QX3YTN0wyMwAzNzEzW}
```
### New Learnings
A File Descriptor (FD) is a number that describes a communication channel in Linux.  

FD 0: Standard Input  
FD 1: Standard Output  
FD 2: Standard Error  
hacker@dojo:~$ some_command > output.log 2> errors.log  
output to output.log and errors in errors.log  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------
## Challenge 5: Redirecting Input


### Solve

**Flag:** `pwn.college{Enjs5jS4D6xKcTKdvM00T-PvnN9.QXwcTN0wyMwAzNzEzW}`

fed COLLEGE as input in PWN file  
told the command /challenge/run to take input from PWN file instead of user typing it  

```bash
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read 
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{Enjs5jS4D6xKcTKdvM00T-PvnN9.QXwcTN0wyMwAzNzEzW}
```
### New Learnings

redirect input to files using < 
In Linux, < just means: “Take input from this file instead of me typing it.”  


### References

Challenge description and CHATGPT for theory clarity.

# ----------------------------------------------------------------------------------------------------------

## Challenge 6: Grepping stored results


### Solve

**Flag:** `pwn.college{cV1cfdru_pfAAwM2O3Xfm5S67Ke.QX4EDO0wyMwAzNzEzW}`

```bash
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
[INFO PRINTED]
hacker@piping~grepping-stored-results:~$ grep pwn /tmp/data.txt
pwn.college{cV1cfdru_pfAAwM2O3Xfm5S67Ke.QX4EDO0wyMwAzNzEzW}
pwning
pwns
pwned
pwn
```
### New Learnings



### References

Challenge description and previous notes.

# ----------------------------------------------------------------------------------------------------------

## Challenge 7: Grepping Live Output


### Solve

**Flag:** `pwn.college{kVbBxTeG0tPW_dJQW_cpZcU0qlT.QX5EDO0wyMwAzNzEzW}`

```bash
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwns
pwn
pwn.college{kVbBxTeG0tPW_dJQW_cpZcU0qlT.QX5EDO0wyMwAzNzEzW}
pwned
pwning
```
### New Learnings

no need to store output into a file first and then search throught it  
pipe  |  does it  
Standard output from the command to the left of the pipe will be connected to (piped into) the standard input of the command to the right of the pipe.  

output | input  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 8: Redirecting Errors


### Solve

**Flag:** `pwn.college{kFWRmsUSHMGWUL2gPuKiCNTLXqv.QX1ATO0wyMwAzNzEzW}`

```bash
hacker@piping~grepping-errors:~$ /challenge/run 2>& 1 | grep pwn
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwned
pwn.college{kFWRmsUSHMGWUL2gPuKiCNTLXqv.QX1ATO0wyMwAzNzEzW}
pwning
pwns
pw
```
### New Learnings

>& operator -  redirects a file descriptor to another file descriptor.  
example- 2>&1 means “send stderr (2) to the same place as stdout (1)”.  
With 2>&1 → errors and normal output get merged.  

ex- command > all_output.txt 2>&1  
 

### References

Challenge description and chatgpt for theory clarity.

# ----------------------------------------------------------------------------------------------------------
## Challenge 9: Filtering with grep -v



### Solve

**Flag:** `pwn.college{AWWKLNa5Ggxs78OXsprneHnUOvg.0FOxEzNxwyMwAzNzEzW}`

```bash
hacker@piping~filtering-with-grep-v:~$ /challenge/run | grep -v DECOY
pwn.college{AWWKLNa5Ggxs78OXsprneHnUOvg.0FOxEzNxwyMwAzNzEzW}
```
### New Learnings
IMP-  

Think of | as a bridge between two separate commands. 

pipe (|): a shortcut to say "take whatever you just printed, and give it as input to the next command."  

-v (invert match).  
 While normal grep shows lines that MATCH a pattern,  
  grep -v shows lines that do NOT match a pattern:

### References

Challenge description and chatgpt for theory clarity.

# ----------------------------------------------------------------------------------------------------------
## Challenge 10: Duplicate piped data with tee



### Solve

**Flag:** `pwn.college{YJgJPjLrWeZ_tJF3L9ujLhWgU-C.QXxITO0wyMwAzNzEzW}`

```bash
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn | tee flag | /challenge/college
Processing...
WARNING: you are overwriting file flag with tee's output...
The input to 'college' does not contain the correct secret code! This code 
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the 
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ cat flag
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "YJgJPjLr"
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret YJgJPjLr | /challenge/college
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{YJgJPjLrWeZ_tJF3L9ujLhWgU-C.QXxITO0wyMwAzNzEzW}
```
### New Learnings

SYNTAX : /command1 | tee saved.txt | /command2  

1. /command1 → produces data.  

tee saved.txt → copies that data into saved.txt and passes it along.  
 
/command2 → gets the exact same data to process.  

2. You could even branch to multiple files:  

/command1 | tee file1.txt file2.txt | /command2  



### References

Challenge description and chatgpt for theory clarity.

# ----------------------------------------------------------------------------------------------------------
## Challenge 11: Process substitution for input 



### Solve

**Flag:** `pwn.college{AnVOpaMgIwlTfhOxKeO03zM38CC.0lNwMDOxwyMwAzNzEzW}`

```bash
hacker@piping~process-substitution-for-input:~$ diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)
56a57
> pwn.college{AnVOpaMgIwlTfhOxKeO03zM38CC.0lNwMDOxwyMwAzNzEzW}
```
### New Learnings

1. process substitution — basically a way to treat a command’s output (or input) like a file  
2. handy in Linux when a program expects a filename, but you want to feed it from another command. (ex- diff here) 
3. diff <(sort file1.txt) <(sort file2.txt)  
---<(...) turns those outputs into temporary “files.”

diff reads from those pseudo-files as if they were real files.  

 


### References

Challenge description and chatgpt for theory clarity.

# ----------------------------------------------------------------------------------------------------------
## Challenge 12: Writing to multiple programs



### Solve

**Flag:** `pwn.college{8CjA8NgzAy1H8eEFXake5nBiJ5P.QXwgDN1wyMwAzNzEzW}`

```bash
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee >(/challenge/the) >(/challenge/planet)
This secret data must directly and simultaneously make it to /challenge/the and 
/challenge/planet. Don't try to copy-paste it; it changes too fast.
7058125493128631186
Congratulations, you have duplicated data into the input of two programs! Here 
is your flag:
pwn.college{8CjA8NgzAy1H8eEFXake5nBiJ5P.QXwgDN1wyMwAzNzEzW}
```
### New Learnings

1.  tee normally splits stdout: it writes to files and also passes the data along.  
ex-  hacker@dojo:~$ echo HACK | tee >(rev)  
HACK  
KCAH  

tee >(rev)  
>(rev) is process substitution.  

Bash turns >(rev) into a special file (like /dev/fd/63) that tee can write to.  

When tee writes to that “file,” the data is fed into the command rev.  

### References

Challenge description and chatgpt for theory clarity.


# ----------------------------------------------------------------------------------------------------------
## Challenge 13: Split piping stderr and stdout



### Solve

**Flag:** `pwn.college{wzqBza12QUmZeRo9rqxljIlV7K3.QXxQDM2wyMwAzNzEzW}`

```bash
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack > >( /challenge/planet ) 2> >( /challenge/the )
Congratulations, you have learned a redirection technique that even experts 
struggle with! Here is your flag:
pwn.college{wzqBza12QUmZeRo9rqxljIlV7K3.QXxQDM2wyMwAzNzEzW}
```
### New Learnings

pipe (|): a shortcut to say "take whatever you just printed, and give it as input to the next command."  

-v (invert match).  
 While normal grep shows lines that MATCH a pattern,  
  grep -v shows lines that do NOT match a pattern:

### References

Challenge description and chatgpt for theory clarity.


# ----------------------------------------------------------------------------------------------------------
## Challenge 14: Named Pipes



### Solve

**Flag:** ``

```bash

```
### New Learnings



### References

Challenge description.


# ----------------------------------------------------------------------------------------------------------

## ADDITIONAL NOTES

1. The usual redirection  

Normally, in Linux you can redirect a program’s output into a file:  
 
echo hello > out.txt  


This puts "hello" inside out.txt.  
Here > means: “send stdout into this file”.  

2. But what if… we want a command instead of a file?  

Sometimes, instead of sending output to a file, we want to send it directly to another command.  

For example:  

echo hello | rev  


Here "hello" goes straight into rev, no file needed.  

But piping (|) has one limitation → it always connects stdout of one command to stdin of another, in sequence.  
What if we want more flexible wiring? (like, stdout to two places, or stderr into a program, not stdout).  

3. Enter process substitution  

Process substitution >(command) pretends that the command is a file.  

Example:  
  
cat > >(rev)  


>(rev) → Bash starts rev running in the background.  

Bash creates a special file (like /dev/fd/63) that is connected to rev’s input.  

cat > writes into that file, so it’s actually writing into rev.  

So:  

To your main command, it looks like a normal filename.  

In reality, it’s a command’s input/output.  

4. Why is this useful?  

It lets you redirect into a program as if it were a file.  

Example:  

echo HELLO > >(rev)  


echo HELLO thinks it’s writing into a file.  

That “file” is secretly hooked to rev.  

So rev sees HELLO and outputs OLLEH.  

Output:  

OLLEH  

5. With stderr and stdout separately  

Normally > only works with stdout.
But you can also use 2> for stderr.  

myprog > >(rev) 2> >(tr a-z A-Z)  


stdout goes into rev  

stderr goes into tr, which uppercases it  


