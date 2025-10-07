# File Globbing 

## Challenge 1: matching-with-*

### Solve

**Flag:** `pwn.college{c00-AEUxerAtZatmNRjawww8Q9E.QXxIDO0wyMwAzNzEzW}`

```bash
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /ch*/r*
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{c00-AEUxerAtZatmNRjawww8Q9E.QXxIDO0wyMwAzNzEzW}
hacker@globbing~matching-with-:/challenge$ ^C
```
### New Learnings

The * matches any part of the filename except for / or a leading . character. For example:  

hacker@dojo:~$ echo ONE: /ho*/*ck*  
ONE: /home/hacker  
hacker@dojo:~$ echo TWO: /*/hacker  
TWO: /home/hacker  
hacker@dojo:~$ echo THREE: ../*  
THREE: ../hacker  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 2: matching-with-?

### Solve

**Flag:** `pwn.college{cmfANbsBpZ_g_h1kqnvg1ZdpOnF.QXyIDO0wyMwAzNzEzW}`

```bash
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /ch*/r*
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{cmfANbsBpZ_g_h1kqnvg1ZdpOnF.QXyIDO0wyMwAzNzEzW}
```
### New Learnings

When it encounters a ? character in any argument, the shell will treat it as a single-character wildcard.   
This works like *, but only matches one character  
hacker@dojo:~$ echo Look: file_?  
Look: file_a file_b  
hacker@dojo:~$ echo Look: file_??  
Look: file_cc  

### References

Challenge description.


# ----------------------------------------------------------------------------------------------------------


## Challenge 3: matching-with-[]

### Solve

**Flag:** `pwn.college{QwTUsFWiBy60ogv6QlwP4fXsWEd.QXzIDO0wyMwAzNzEzW}`

```bash
hacker@globbing~matching-with-:~$ cd /*/files
hacker@globbing~matching-with-:/challenge/files$ file_[ab]
bash: file_a: command not found
hacker@globbing~matching-with-:/challenge/files$ echo Look: file[ab]
Look: file[ab]
hacker@globbing~matching-with-:/challenge/files$ echo Look: file_[ab]
Look: file_a file_b
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[bash]
You got it! Here is your flag!
pwn.college{QwTUsFWiBy60ogv6QlwP4fXsWEd.QXzIDO0wyMwAzNzEzW}
```
### New Learnings

Instead of matching any character, [] is a wildcard for some subset of potential characters, specified within the brackets   
hacker@dojo:~$ echo Look: file_[ab]  
Look: file_a file_b  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 4: matching-paths-with-[]

### Solve

**Flag:** `pwn.college{w0toFGf1rrHgC4rgz9eL17HcpHu.QX0IDO0wyMwAzNzEzW}`

```bash
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{w0toFGf1rrHgC4rgz9eL17HcpHu.QX0IDO0wyMwAzNzEzW}
```
### New Learnings

Instead of matching any character, [] is a wildcard for some subset of potential characters, specified within the brackets   
used for paths as well  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 5: Multiple Globs

### Solve

**Flag:** `pwn.college{UeoRQ0RtkDhB0R0YUZU751Xy3Yi.0lM3kjNxwyMwAzNzEzW}`

```bash
hacker@globbing~multiple-globs:~$ cd /*/files
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{UeoRQ0RtkDhB0R0YUZU751Xy3Yi.0lM3kjNxwyMwAzNzEzW}
```
### New Learnings

What happens above is that the shell looks for all files in / that start with anything (including nothing), then have an f and an l, and end in anything (including ag, which makes flag). 

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 6: Mixing Globs

### Solve

**Flag:** `pwn.college{cSzRgPFqhZR4LszcrFdtDDFzsHT.QX1IDO0wyMwAzNzEzW}`

```bash
hacker@globbing~mixing-globs:~$ cd /*/files
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
You got it! Here is your flag!
pwn.college{cSzRgPFqhZR4LszcrFdtDDFzsHT.QX1IDO0wyMwAzNzEzW}
```
### New Learnings

path/[multiple file names initial]* 

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 7: Exclusionary Globbing

### Solve

**Flag:** `pwn.college{UdozO1lc-t4JaP5EyLkCi8HRK5J.QX2IDO0wyMwAzNzEzW}`

```bash
hacker@globbing~exclusionary-globbing:~$ cd /*/files
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*
You got it! Here is your flag!
pwn.college{UdozO1lc-t4JaP5EyLkCi8HRK5J.QX2IDO0wyMwAzNzEzW}
```
### New Learnings

 If the first character in the brackets is a ! or (in newer versions of bash) a ^, the glob inverts, and that bracket instance matches characters that aren't listed.   
 hacker@dojo:~$ ls  
file_a	file_b	file_c  
hacker@dojo:~$ echo Look: file_[!ab]  (OR hacker@dojo:~$ echo Look: file_[^ab])
Look: file_c    

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 8: Tab completion

### Solve

type first letter then press tab and let shell complete it

**Flag:** `pwn.college{IQr7jCbi8YvU8UJVu-bn-dBArYV.0FN0EzNxwyMwAzNzEzW}`

```bash
hacker@globbing~tab-completion:~$ cat /challenge/pwncollege​ 
pwn.college{IQr7jCbi8YvU8UJVu-bn-dBArYV.0FN0EzNxwyMwAzNzEzW}
```
### New Learnings

when you are trying to specify a specific target is tab completion.  
 If you hit tab in the shell, it'll try to figure out what you're going to type and automatically complete it

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 9: Multiple Options for Tab completion

### Solve

**Flag:** `pwn.college{Eau1-TUWA2T6kdyOZIvHtkId69F.0lN0EzNxwyMwAzNzEzW}`

```bash
hacker@globbing~multiple-options-for-tab-completion:~$ cd /challenge/files/
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ /challenge/files/pwn
pwn                    pwn-the-planet         pwncollege-flamingo    pwncollege-hacking     
pwn-college            pwncollege-family      pwncollege-flyswatter  
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat pwncollege-flag
pwn.college{Eau1-TUWA2T6kdyOZIvHtkId69F.0lN0EzNxwyMwAzNzEzW}
```
### New Learnings

What happens varies based on the specific shell and its options.   
By default bash will auto-expand until the first point when there are multiple options (in this case, fl).  
 When you hit tab a second time, it'll print out those options. Other shells and configurations, instead, will cycle through the options.

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 10: Tab Completion on commands

### Solve

**Flag:** `pwn.college{gM0ciJOJZWoG02EKtTsCracbILb.0VN0EzNxwyMwAzNzEzW}`

```bash
hacker@globbing~tab-completion-on-commands:~$ pwncollege-1052 
Correct! Here is your flag:
pwn.college{gM0ciJOJZWoG02EKtTsCracbILb.0VN0EzNxwyMwAzNzEzW}
```
### New Learnings
tab complete also works with commands

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------


